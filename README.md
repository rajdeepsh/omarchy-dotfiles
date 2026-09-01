# omarchy-dotfiles

## Setup
### Monitors
```lua
local omarchy_gdk_scale = 1.75
hl.env("GDK_SCALE", tostring(omarchy_gdk_scale))
hl.monitor({ output = "desc:ASUSTek COMPUTER INC XG27AQDMG S5LMRS002727", mode = "2560x1440@240", position = "0x0", scale = 1.6 })

local omarchy_gdk_scale = 2
hl.env("GDK_SCALE", tostring(omarchy_gdk_scale))
hl.monitor({ output = "desc:Samsung Display Corp. ATNA40CU05-0", mode = "2880x1800@120", position = "0x0", scale = "auto" })
```
### Input
```lua
hl.config({
  input = {
    kb_options = ctrl:nocaps,altwin:swap_alt_win
  }
})
```
### GitHub
```bash
gh auth login
```
