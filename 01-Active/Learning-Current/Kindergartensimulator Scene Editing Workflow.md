# Kindergartensimulator – Scene Editing Workflow

How to change the world without breaking the machine-owned contract. Code tour: [[Kindergartensimulator SceneCreator Walkthrough]].

## The two-layer contract (constitution rule 13, design-v2 §6.3)

| | `Kindergarten.unity` | `Decoration.unity` |
|---|---|---|
| Owner | **Machine** — regenerated wholesale by `SceneCreator` | **Human** — hand-edited, never regenerated |
| Contains | Everything gameplay-bound: rooms, anchors, markers, NavMesh, lights, every name code/config/tests reference | Pure set-dressing: props, plants, clutter, wall art |
| Loaded | Main scene | Additively at startup by `GameBootstrap` |
| Behavior | Yes | **Never** — no scripts, no colliders that matter, nothing referenced by code |
| Hand edits | **Transient** — lost on next regeneration unless ported into `SceneCreator` | Permanent — this *is* the authoring surface |

## Which edit goes where — decision table

| I want to… | Layer | How |
|---|---|---|
| Add a purely visual prop nothing will ever reference | `Decoration.unity` | Place by hand (or via MCP: place → screenshot → adjust). Done — no code. |
| Move/rotate/rescale existing furniture or props | `SceneCreator` | Edit the entry in `FurnitureTable` / `PlacePlayground` / etc., regenerate. |
| Add a new deco prop *inside the generated world* that should survive regeneration | `SceneCreator` | New `FurniturePlacement` with a `Deko_*` name, `isAnchor: false`. |
| Add a new gameplay object (interactable, POI, spawn) | `SceneCreator` **+ config** | `Anchor_*` entry or marker table; POIs also need the matching `roam.pois` id in `config.json`; smoke tests may need the name. |
| Change walls/rooms/roof/terrain (structural) | `SceneCreator` | Edit the build methods; check the coupled-values list below. |
| Change lights | `SceneCreator` + re-bake | `BuildLights` values, regenerate, **re-bake lightmaps**. |
| Rebalance/tune gameplay numbers | Not the scene | `Assets/StreamingAssets/config.json`. |

## The regeneration loop

1. Edit `SceneCreator.cs` (or first prototype by hand in the editor — see below).
2. `refresh_unity` (compile) via MCP; check console clean.
3. Regenerate: `execute_code` → `Game.Unity.Editor.SceneCreator.CreateGameScene();` — commit/shelve first if uncommitted work is in the scene (constitution rule 10: commit before large MCP editor operations).
4. Verify: screenshot pass for looks; `run_tests` — the scene smoke tests check anchors/POIs/NavMesh presence.
5. **If lamps or layout changed: re-bake lighting** (bake is *not* part of regeneration; Progressive CPU lightmapper).
6. Zero console errors/warnings → commit (scene file + code together).

## Hand-tweak → backport (the current convention)

Until the capture tool exists, hand-editing the generated scene is a *scratchpad*, not authoring:

1. Regenerate to a known-clean state.
2. Move things freely in the editor until it looks right (or let an agent do it via MCP).
3. Read the final values from the Inspector and port them into the matching table/constant in `SceneCreator.cs`.
4. Regenerate and confirm the scene reproduces your arrangement. Only the code change gets committed — the scene diff should be exactly what the code produces.

Backporting pitfalls:

- **Y is usually computed.** Most furniture auto-grounds (`y = -bounds.min.y`); only port X/Z/rotation/scale. If you changed Y on a wall-mounted prop, that's the `explicitY` parameter.
- **Kitchen row, shelf toys, counter dressing, WickelPad, knife, ToiletSeatPoint are bounds-derived** — their positions follow other objects. Port the *inputs* (order, scale, dx/dz offsets), not the resulting world positions.
- **Scattered vegetation/forest is seeded-random.** You can't hand-move one grass tuft persistently; change the seed, counts, bounds, or exclusion zones instead.

## Coupled values — the trap list

One conceptual change often lives in several places. Grep before assuming one edit is enough:

- **Playground prop positions** are encoded 3×: `PlacePlayground` (the props), `BuildPois` (the matching POI markers), `ScatterVegetation` exclusion circles. Move the slide → update all three.
- **Building footprint** (x −13..7, z −5..5) appears in: floor block, wall runs, roof extents (incl. hardcoded gable ends at x=−13/7), ceiling slab, probe area (`ProbeAreaMin/Max`), `TerrainHeight` plot rectangle, `BuildForest`'s `Blocked()` rectangle, window/flyer wall-face offsets.
- **WC doorway** (1.0 m at z −3.6..−2.6): wall gap ↔ door panel width ↔ `ToiletSeatPoint` look-target ↔ scare direction points.
- **POI ids** ↔ `config.json` `roam.pois` ↔ physical prop positions.
- **`Anchor_*` and marker names** ↔ runtime `GameObject.Find` ↔ `SceneSmokeTests`. Renaming is an API break.
- **Any lamp/geometry change** ↔ stale lightmaps until re-baked; probes/GI flags regenerate automatically, the bake doesn't.

## Tried & deferred: hand-sculpted Umgebung Terrain (FR-87, reverted 2026-07-20)

Ground + forest briefly moved to a Unity Terrain in `Decoration.unity`, then reverted — the generated Perlin mesh + seeded forest stay for now. Worth revisiting once the capture tooling below exists.

## Planned: layout-data + capture tool ("Approach B", approved 2026-07-20)

Agreed but not yet built — the fluid version of this workflow:

1. Extract the placement tables (furniture, playground, windows, POIs, flyer points, spawns, lights) from C# into one layout data file; `SceneCreator` keeps the *how*, data holds the *what/where* (constitution rule 7 applied to layout).
2. A small `SceneLayoutCapture` editor utility writes hand-moved objects' transforms back into that data file.
3. Loop becomes: regenerate → move things in the editor → capture → regenerate to verify → commit a readable data diff. Structural code (walls, roof, terrain, scatter logic) stays code.
