# omarchy-dotfiles

## Setup
### Input
```lua
hl.config({
  input = {
    kb_options = "ctrl:nocaps,altwin:swap_alt_win",
    touchpad = {
      natural_scroll = true,
    },
  },
})
```
### Keybindings
```lua
hl.unbind("SUPER + SHIFT + A")
o.bind("SUPER + SHIFT + A", "Claude", { webapp = "https://claude.ai" })
```
### GitHub
```bash
gh auth login
```
