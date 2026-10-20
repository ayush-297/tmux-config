# tmux keybindings

Quick reference for this config. **Prefix is `Ctrl+j`** (secondary: `Ctrl+f`). "prefix x" means press the prefix, release, then press `x`.

The status bar shows **PREFIX** while tmux is waiting for the next key.

## Sessions

| Keys / command | Action |
|---|---|
| `tmux` | Start a new session |
| `tmux new -s name` | Start a named session |
| `tmux ls` | List sessions |
| `tmux attach -t name` | Reattach to a session |
| prefix `d` | Detach (session keeps running) |
| prefix `s` | Pick a session from a list |
| prefix `$` | Rename session |

## Windows (tabs)

| Keys | Action |
|---|---|
| prefix `c` | New window |
| prefix `,` | Rename window |
| prefix `&` | Close window |
| prefix `1`…`9` | Go to window by number (numbering starts at 1) |
| prefix `w` | Pick a window from a list |
| `Shift + ←` / `Shift + →` | Previous / next window (no prefix) |
| `Ctrl + Shift + ←` / `→` | Move window left / right (no prefix) |

## Panes (splits)

| Keys | Action |
|---|---|
| prefix `v` | Split side by side |
| prefix `h` | Split top / bottom |
| `Option + ← ↑ ↓ →` | Move between panes (no prefix) |
| prefix `z` | Zoom / unzoom pane (`[Z]` shows on the tab) |
| prefix `x` | Close pane |
| prefix `q` | Show pane numbers |
| prefix `Ctrl + arrow` | Resize pane by 1 cell (repeatable) |
| prefix `Option + arrow` | Resize pane by 5 cells (repeatable) |
| prefix `Space` | Cycle pane layouts |
| prefix `!` | Turn pane into its own window |
| prefix `y` | Toggle synchronized panes (typing goes to all; **SYNC** shows in the status bar) |

Repeatable keys (like resizing) can be pressed again within 400 ms without the prefix.

## Copy mode (vi keys)

| Keys | Action |
|---|---|
| prefix `[` | Enter copy mode (scroll back) |
| `v` | Start selection |
| `y` | Copy selection to the macOS clipboard |
| `/` / `?` | Search forward / backward (`n` / `N` for next / previous) |
| `q` | Exit copy mode |
| prefix `p` | Paste tmux buffer |

Mouse support is on: scroll to enter copy mode, drag to select, click to focus panes.

## Misc

| Keys | Action |
|---|---|
| prefix `r` | Reload `~/.tmux.conf` |
| prefix `L` | Clear pane scrollback history |
| prefix `t` | Show a clock |
| prefix `:` | tmux command prompt |
| prefix `?` | List all key bindings |
| `Ctrl+j Ctrl+j` | Send a literal `Ctrl+j` to the program |

## Terminal notes

- `Option` must act as Meta/Alt for the `Option + arrow` bindings (kitty: `macos_option_as_alt yes`; VS Code: `terminal.integrated.macOptionIsMeta`).
- kitty uses `Ctrl+Shift+←/→` for its own tabs by default; unmap them (`map ctrl+shift+left no_op`) so they reach tmux.
- Inside tmux, `Ctrl+j` and `Ctrl+f` never reach the running program (e.g. Neovim, zsh). Press the prefix twice to send `Ctrl+j`.
