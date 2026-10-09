# tmux-config

My tmux configuration for macOS. It uses no plugins and has a Catppuccin Mocha colour scheme.

## Install

```sh
git clone git@github.com:ayush-297/tmux-config.git ~/tmux-config
ln -sf ~/tmux-config/.tmux.conf ~/.tmux.conf
tmux source-file ~/.tmux.conf
```

## Prefix

`C-j` (primary) and `C-f` (secondary). Press `C-j C-j` to send a literal `C-j`.

## Key bindings

| Keys | Action |
|---|---|
| `prefix v` | Split side by side |
| `prefix h` | Split top / bottom |
| `Option + ←↑↓→` | Move between panes (no prefix) |
| `Shift + ← / →` | Previous / next window (no prefix) |
| `Ctrl + Shift + ← / →` | Move window left / right (no prefix) |
| `prefix y` | Toggle synchronized panes (shows **SYNC** in the status bar) |
| `prefix r` | Reload config |
| `prefix L` | Clear scrollback history |
| `prefix p` | Paste buffer |
| `prefix z` | Zoom pane (shows `[Z]` on the window tab) |

## Copy mode (vi keys)

`prefix [` to enter, `v` to start a selection, `y` to copy to the macOS clipboard (`pbcopy`). Mouse support is on.

## Notes

- Windows and panes are numbered from 1.
- `repeat-time` is 400ms, so repeatable keys (like resizing) can be pressed again without the prefix.
- The status bar shows **PREFIX** while tmux is waiting for a key after the prefix.
- Option-key bindings need your terminal to treat Option as Meta. In VS Code that's `terminal.integrated.macOptionIsMeta`.
