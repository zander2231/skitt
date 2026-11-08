# skitt

A tabletop simulator built in Godot.

## Engine & project settings

- Godot **4.7** (`/opt/homebrew/bin/godot`, also `/Applications/Godot.app`)
- Renderer: **GL Compatibility** (desktop and mobile). Avoid Forward+-only features (SDFGI, volumetric fog, compute shaders, etc.).
- 3D physics: **Jolt**
- Stretch mode `canvas_items`, aspect `expand`

## Layout

- `project.godot`: engine config. Prefer changing it through the editor; edit by hand only for simple keys.
- `design-docs/`: design notes for the game. Read the relevant ones before building a feature.
- `.godot/`: editor cache. It is git-ignored; never edit it.

## Conventions

- Language: GDScript with static typing (`var x: int`, typed function signatures).
- Files and folders: `snake_case`. Classes (`class_name`): `PascalCase`.
- Keep each scene next to its script (`foo.tscn` + `foo.gd`).
- `.tscn`/`.tres` files are text and can be edited directly. Prefer the editor (or the godot-ai MCP when it is connected) for non-trivial scene changes, and keep `uid://` references intact.
- Line endings are LF and files are UTF-8 (see `.gitattributes` and `.editorconfig`).

## Running & checking

- Run the game: `godot --path .`
- Open the editor: `godot --path . --editor`
- Check scripts without opening a window: `godot --headless --path . --check-only --script res://path/to/script.gd`
- Re-import assets after adding files outside the editor: `godot --headless --path . --import`
