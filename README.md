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
hl.unbind("SUPER + SHIFT + S")
o.bind("SUPER + SHIFT + S", "Screenshot", "omarchy-capture-screenshot")
hl.unbind("SUPER + SHIFT + D")
o.bind("SUPER + SHIFT + D", "Telegram", { webapp = "https://web.telegram.org", focus = true })
```
### GitHub
```bash
gh auth login
```
