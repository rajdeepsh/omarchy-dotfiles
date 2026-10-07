# omarchy-dotfiles

Personal configuration overrides for an Omarchy (Arch + Hyprland) system.

## Layout

Top-level directories in this repo mirror the same paths under `~` on the
local system. Everything under `.config/` maps to `~/.config`, and `.claude/`
maps to `~/.claude`:

| Repo path                        | Local path                        |
|----------------------------------|-----------------------------------|
| `.config/hypr/bindings.lua`      | `~/.config/hypr/bindings.lua`     |
| `.config/hypr/input.lua`         | `~/.config/hypr/input.lua`        |
| `.config/lazygit/config.yml`     | `~/.config/lazygit/config.yml`    |
| `.config/zathura/zathurarc`      | `~/.config/zathura/zathurarc`     |
| `.claude/settings.json`          | `~/.claude/settings.json`         |

## `sync` command

When asked to "sync", push every file under `.config/` and `.claude/` in this
repo to its local counterpart. The two directories are handled differently.

### `.config/`: copy

Copy each repo file over the local file with `cp`, creating parent
directories as needed. The local file ends up identical to the repo file.
Use plain `cp`, never `mv` or `cp --remove-destination`, so that if the local
path is a symlink the copy writes through to its target and the link stays
intact.

### `.claude/`: merge

Never replace the local file wholesale. Parse `.claude/settings.json` and
`~/.claude/settings.json` as JSON, then for each top-level key in the repo
file:

- If the key already exists locally, update it to the repo value.
- If the key does not exist locally, add it.

Keys that only exist locally are left untouched. Write the result back with
two-space indentation. If the local file does not exist, create it with the
repo contents.

After syncing, show a diff of each changed local file. Do not commit anything
during a sync; it only writes to `~/.config` and `~/.claude`.

## Conventions

- Keep repo files minimal: only the lines that differ from Omarchy defaults.
- Commit messages describe the user-facing change, for example
  "Add Omarchy update hotkey".
