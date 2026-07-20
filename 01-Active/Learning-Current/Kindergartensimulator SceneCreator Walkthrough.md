# Kindergartensimulator – SceneCreator Walkthrough

A guided tour of `Assets/Game/Unity/Editor/SceneCreator.cs` (~1370 lines) — the script that generates the entire machine-owned `Kindergarten.unity` scene from scratch. Companion note: [[Kindergartensimulator Scene Editing Workflow]] (how to actually make changes safely).

The one-sentence mental model: **the scene file is a build artifact, the C# file is the source.** Everything in `Kindergarten.unity` — geometry, furniture, markers, lights, NavMesh — is deterministically reproducible by running one method. Hand edits to the scene are lost on the next regeneration unless ported back into this file.

## How to run it

- **Editor open (preferred):** via the MCP bridge, `execute_code` → `Game.Unity.Editor.SceneCreator.CreateGameScene();`
- **CLI:** `Unity -batchmode -nographics -projectPath . -executeMethod Game.Unity.Editor.SceneCreator.CreateGameScene -logFile -` — the method calls `EditorApplication.Exit(0)` itself when in batch mode, so no `-quit`.

Regeneration starts from a **completely empty scene** (`NewSceneSetup.EmptyScene`) — it never patches the existing scene, it rebuilds the world wholesale and saves over `Assets/Game/Scenes/Kindergarten.unity`.

## Entry point: `CreateGameScene()`

1. New empty scene; create the `Bootstrap` GameObject with the `GameBootstrap` component. (At runtime, `GameBootstrap` builds everything *dynamic*: kids, UI, flyer views, interactable wiring. SceneCreator only builds the static world it operates on.)
2. `BuildWorld()` — see build order below.
3. Assign the lighting settings asset `Assets/Settings/KindergartenLighting.lighting` to the scene.
4. Save the scene; `EnsureDecorationScene()` creates `Decoration.unity` **empty, once, only if missing** — it is never touched again (the human-owned layer).
5. Register both scenes in the build settings.

## Build order (`BuildWorld`) — order matters

```
BuildIndoorFloor    → BuildWalls → BuildRoof → BuildWcDoor
BuildFurniture      (incl. kitchen row, windows, shelf toys)
BuildScissorsProp   (knife hazard — needs Basteltisch to exist first)
BuildGarten         (floor, fences, playground, vegetation, cigarette corner)
BuildUmgebung       (terrain, road + car park, town, forest, car pool)
BuildFlyerPoints → BuildKidSpawns → BuildPois
BuildLights → BuildLightProbes → MarkGiContributors
BakeNavMesh         (LAST — it consumes every physics collider placed above)
```

Two ordering rules to remember:

- Several builders **find previously created objects by name** (`GameObject.Find("Basteltisch")`, `"Shelves"`, `"KuecheCounter_2"`, `"Anchor_Toilet"`, wall segments for probe blocking). Anything that measures or decorates another object must run after it.
- **NavMesh is baked from physics colliders**, so it must run after every collider exists. It runs automatically on every regeneration — no manual NavMesh step.

## The world map (top-down, meters; x → east, z → north)

```
z=5  ┌──────────────┬─────────────────────────┐
     │  Küche       ╎gap                      │   Building: x −13..7, z −5..5
z=0  ├──────────────┤      Gruppenraum        │   (floor block 20×10 at center −3,0)
     │  WC          ╎gap                      │
z=−5 └──────────────┴───╴ ╶───────────────────┤─┐ ← main door: gap x −1..1
     │            Garten  x −7..9, z −13..−5  ├─┘
z=−13└───────────── fence ────────────────────┘
z=−14   car park (2 marked spaces)
z=−20   road, east–west (10 m Pandazole tiles, x −40..40)
z=−30   town row (6 resident buildings)
        forest scatter: x ±44, z −44..36 · terrain mesh: x −46..46, z −46..38
     x=−13          x=−7                   x=7  x=9
```

- **Küche** x −13..−7, z 0..5 · **WC** x −13..−7, z −5..0 · **Gruppenraum** x −7..7, z −5..5.
- Doorways are *gaps in wall runs*: main entrance at z=−5 (x −1..1, Gruppenraum → Garten); on the x=−7 divider (`Wall_Mid_Vertical`): z −3.6..−2.6 → WC (exactly 1.0 m so the door panel seals it, FR‑75) and z 2..3.6 → Küche. The Küche/WC divider (`Wall_Mid_Horizontal`, z=0) has no gap — the WC is entered from the Gruppenraum.
- Wall height 3.2 m (`WallHeight`), gable roof ridge at 5.1 m.

## Helper vocabulary — the eight workhorses

Nearly everything is built with these; learn them and the rest of the file reads easily.

| Helper | What it does |
|---|---|
| `MakeBlock(name, pos, scale, color)` | Primitive cube + URP Lit material tinted via `_BaseColor`. Comes **with** a BoxCollider (destroy it explicitly for visual-only blocks). |
| `MakeChildBlock(parent, …)` | Same, parented with local position/scale. |
| `TintShared(go, color)` | Creates a **fresh** URP Lit material per object and assigns it (materials are per-object instances, not shared assets). |
| `WorldBounds(go)` | Union of all child renderer bounds in world space. The basis of every "place X on top of Y" calculation. |
| `InstantiateFurniture(path, name, x, z, yRot, isAnchor, explicitY, scale)` | The furniture engine, see below. |
| `PlacePackProp(path, name, x, z, yRot, withCollider)` | `InstantiateFurniture` at scale 1; optionally adds a bounds-fitted BoxCollider if the prefab has none. Logs each prop's world size for scale sanity checks. |
| `BuildWallRun(prefix, horizontal, from, to, fixed, h, t, color, gaps…)` | Splits a wall line into solid `{prefix}_{i}` blocks around door gaps. |
| `BuildFenceRun(name, horizontal, from, to, fixed)` | Picket-fence prefab tiled to fit the run length (visual, collider-free) **plus one invisible full-length collider box** that actually contains players/kids and bounds the NavMesh. |

### `InstantiateFurniture` in detail

- Loads the prefab, scales it (`FurnitureScale = 0.25` default because the Kenney FBX kit imports ~4× life-size; the newer packs pass explicit scales, mostly 1–3.5).
- Measures `WorldBounds` at the origin, then **grounds it automatically**: `y = explicitY ?? -bounds.min.y` — the model sits exactly on the floor (y=0) no matter where its pivot is. `explicitY` is only for wall-mounted things (clock, paintings, mirror) and special cases.
- `isAnchor: true` adds a BoxCollider fitted to the render bounds (converted into local space by dividing out the scale). Anchors are what the player interacts with; the collider is their hitbox.

## Placement tables (declarative data inside the code)

- **`FurnitureTable`** (`FurniturePlacement[]`, ~50 entries) — the master furniture list: `(prefabPath, name, x, z, yRotation, isAnchor, explicitY?, scale?)`. Grouped by room in the source. Names starting with `Anchor_` are gameplay; `Deko_` is visual-only.
- **Windows** (`BuildWindows`) — a tuple table of `(name, x, z, rot)`; each spot gets a primitive sky-blue pane + sill assembly stuck to the interior wall face (x/z ≈ wall face ± 0.18).
- **Playground** (`PlacePlayground`) — sandbox, slide (`Rutsche`), swings (`Schaukel`), two benches, two garden trees, each one `PlacePackProp` call.
- **POIs / flyer points / kid spawns** — plain coordinate tables, see "Markers" below.
- **Town** (`BuildTown`) — six houses in a row plus seeded bushes.

## Derived placements — these positions are computed, not typed

Important when hand-tweaking: you **cannot** freely move these in the editor and expect a single number to capture it — they follow other objects' bounds.

- **Kitchen row** (`BuildKitchenRow`): fridge (`Anchor_Cheese`), sink, counter, stove (`Anchor_Herd`) are laid out as a *flow layout* — a cursor starts at x=−12.92, each unit is measured via `WorldBounds` and placed flush (2 cm gap), backs against the north wall inner face (z=4.85). Change the order or scale, and every position shifts automatically.
- **Counter dressing** (`DressKitchenCounters`): pot/board/bread placed relative to `KuecheCounter_2`'s bounds top.
- **Shelf toys** (`PlaceToysOnShelves`): toys sit on `bounds.max.y` of the found shelf.
- **Wickeltisch**: table placed normally, then the white `WickelPad` sized/positioned from the table's measured bounds.
- **Knife hazard** (`BuildScissorsProp`): `Anchor_Scissors` snaps to the `Basteltisch` table top (falls back to fixed coords if the table is missing). Core still calls it "scissors"; the pack has no scissors, so the prop is `Prop_Knife_01` (user-approved).
- **`ToiletSeatPoint`**: the seated-camera eye pose, computed from the toilet's bounds, looking at the WC doorway center (−7, y, −3.1).

## Procedural geometry & determinism

- **Terrain** (`BuildTerrainMesh` + `TerrainHeight`): a 2 m-grid mesh displaced by Perlin noise, flattened to zero under two rectangles (kindergarten plot x −15..11/z −15..7; road/car-park/town corridor z −36..−12) with a 7 m soft falloff between. Deliberately **no collider** — the NavMesh must not spill outside the fence. *(An FR-87 attempt to replace this with a hand-sculpted Unity Terrain in Decoration was reverted 2026-07-20 — revisit after the layout-capture tooling exists.)*
- **Roof** (`BuildRoof`): procedural gable mesh (two slopes + two gable triangles), each face emitted **twice with separate vertex copies** (one per winding). Sharing vertices between both windings made `RecalculateNormals` average opposing normals to zero → the roof rendered black (the FR‑84 bug). Under it: flat light `Decke` ceiling slab, collider destroyed.
- **Scatters** — forest trees/undergrowth (`BuildForest`, LPW-only per FR-86), verge bushes, garden grass (`ScatterVegetation`, 280 tufts) — all use **seeded `System.Random`** (seeds 20260719/20/21): rejection-sampling inside bounds, with exclusion zones (building plot, road strip; grass avoids 1.8 m circles around the three play props). Seeded ⇒ every regeneration produces the identical scene; this is the project's determinism rule applied to the editor side.
- **Car pool** (`BuildCarPool`): four deactivated cars parked at y=−50 at 0.65× scale — a pool the runtime traffic director activates for drive-bys; plus one parked car with hand-set offsets.

## Markers the runtime reads by name

`SceneCreator` bakes empty GameObjects the runtime and tests locate via `GameObject.Find` — **names are load-bearing** (see the name contract in [[Kindergartensimulator Scene Editing Workflow]]):

- `Anchor_*` — interaction points: `Anchor_Toilet`, `Anchor_Waschbecken`, `Anchor_Bandage`, `Anchor_Attend`, `Anchor_Snus`, `Anchor_Cheese`, `Anchor_Herd`, `Anchor_Scissors`, `Anchor_Zigarette`.
- `Pois/Poi_<id>` — one marker per `roam.pois` id in `config.json` (`sandkasten`, `rutsche`, `schaukel`, `garten_wiese`, `spielteppich`, `basteltisch`, `gruppenraum_mitte`, `kueche_tisch`). **Ids must match the config**, positions should match the physical props.
- `FlyerPoints_{gruppenraum,kueche,garten}/Point_i` — flyer papers lie flat 0.03 m above the floor, pulled ~0.25 m inside wall faces so they don't clip.
- `KidSpawns/Spawn_i` — 12 spawn spots (Gruppenraum, Basteltisch cluster, Garten).
- `CarRoad/CarSpawn_{West,East}` — lane endpoints for the traffic director; `CarPool/PoolCar_i`.
- `WcDoor` — the door hinge; carries the `AudioSource` with the slam clip (played by `JumpScareDirector`). The panel is deliberately collider-free: doors are visual-only, nothing may physically seal the doorway.

## Collider policy (drives the NavMesh)

The NavMesh bake (`BakeNavMesh`) uses `NavMeshSurface` with **PhysicsColliders** geometry, `CollectObjects.All`, saved to `Assets/Game/Scenes/KindergartenNavMesh.asset`. So colliders = walkability:

- **Has collider:** floor, walls, anchor furniture (bounds-fitted boxes), playground props with `withCollider: true`, the invisible fence blocker boxes.
- **Collider destroyed on purpose:** all outside scenery (road, town, forest, cars), grass/vegetation (walkable through), toys/dressing props, windows, roof/ceiling, door panel + frame, terrain.

Rule of thumb: if kids should walk through/over it or it lives outside the fence, its colliders are stripped at instantiation.

## Lighting

- **Sun**: directional, 55°/−35°, near-white (a golden-hour tint at a midday angle read wrong and pushed everything amber — the warm look comes from the lamps + wall bounce instead). **Soft shadows on** — without them the sun shines straight through the roof and flattens the interior.
- **Ambient**: Skybox mode at 0.3 intensity (cut from the old 1.0 flood so the lamps carry the rooms), reflections 0.5.
- **Ceiling lamps** (`BuildCeilingLight`): 4 point lights (Gruppenraum ×2 @ 12, Küche @ 10, WC @ 8), warm white `(1, 0.93, 0.84)` — kept near-neutral because the orange walls already bounce warmth everywhere; stronger tints collapsed the palette (FR‑84 post-mortem). `LightmapBakeType.Mixed`: movers are lit directly, bounce is baked. Each carries a visible pendant-disc fixture. Shadow resolution is forced to Medium via a `SerializedObject` hack (the property is read-only in the API) — 4 point lights × 6 cube faces don't fit the shadow atlas at High.
- **Light probes** (`BuildLightProbes`): an 11×6 grid × 3 heights over the interior, points inside interior walls culled, plus a 4-point ring under each lamp — so kids/player pick up baked lamp light while moving.
- **GI contributors** (`MarkGiContributors`): only meshes that have a UV2 channel *and* are built-in primitives get `ContributeGI` — the imported pack meshes mostly lack UV2 and would fail the bake.
- ⚠️ **The lightmap bake itself is NOT part of regeneration.** SceneCreator only generates the bake *inputs*. After any lamp or layout change: regenerate, then re-bake (Progressive **CPU** lightmapper — this machine has no OpenCL, the GPU lightmapper silently aborts). Baked artifacts live in `Assets/Game/Scenes/Kindergarten/`.

## Sibling files

- `KenneyMaterials.cs` — `CreateAll()` generates URP materials for the Kenney kits into `<kit>/Materials/`.
- `Builds.cs` — `BuildLinux` / `BuildWindows` player builds (Windows module not installed yet).
