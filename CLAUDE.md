# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repository is

A personal Obsidian vault (markdown knowledge base), not a software project. There are no build, lint, or test commands. Content covers university coursework (MCI), computer science, languages, and creative writing. Much of the content is in German, and German file/folder names are intentional — do not translate or rename them.

## Git: automated by obsidian-git

The obsidian-git plugin auto-commits every 5 minutes with messages like `vault backup: YYYY-MM-DD HH:MM:SS` and auto-pulls every 4 minutes. Consequences:

- The working tree and history can change while you work; expect unrelated `vault backup` commits to appear.
- Uncommitted changes you see in `git status` are usually just notes awaiting the next auto-commit, not work in progress to be careful around.
- Don't commit or push manually unless asked; the plugin handles it. Merge conflicts from the automation occasionally happen and may need manual resolution.

## Structure (PARA)

- `00-Inbox/` — unprocessed captures; items get moved out weekly into the folders below
- `01-Active/` — current projects (e.g. `Learning-Current/`, `Presentation-Matrix-Client/`)
- `02-Areas/` — ongoing topics: `Academia/`, `Computer-Science/`, `Languages/`, `MCI/`, `Programmierung/`, `Development Hobby Projects/`
- `03-Resources/` — reference material and `Templates/`
- `04-Archive/` — completed projects and old writing
- `05-Meta/` — vault management notes (includes an older, partially outdated CLAUDE.md kept for history; this root file is authoritative)
- `Assets/` — all media, centralized: `Images/`, `Excalidraw/`, `Documents/`, `Other/`

Loose files at the vault root and the `IT/` folder are unsorted material that hasn't been filed into PARA yet; when filing content, move it into the structure above rather than adding new top-level folders.

## Conventions

- Internal links use Obsidian wikilink syntax `[[filename]]`; when moving or renaming notes, update links that point to them.
- Media references should use the centralized `Assets/` paths (e.g. `[[Assets/Images/foo.png]]`).
- `.excalidraw.md` files are Excalidraw diagrams (JSON embedded in markdown) — edit them through Obsidian, not by hand.
- Notes may use plugin-specific syntax: Templater templates in `03-Resources/Templates/`, Advanced Slides presentations, Advanced Canvas files. Preserve such syntax when editing.
- This is someone's personal knowledge base: prefer small, targeted edits over sweeping reorganizations, and don't delete or restructure content unless explicitly asked.
