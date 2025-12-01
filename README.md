# yukinord-tmux

A simplified fork of [tokyo-night-tmux](https://github.com/janoamaral/tokyo-night-tmux) - all credit goes to the author.

Updated colors to match the [yukinord.nvim](https://github.com/adibhanna/yukinord.nvim) colorscheme.

## Installation

```bash
# Add to your tmux.conf
set -g @plugin "adibhanna/yukinord-tmux"

# Or for local installation
run-shell ~/path/to/yukinord-tmux/yukinord.tmux
```

## Configuration

```bash
# Optional settings
set -g @yukinord-tmux_window_id_style none      # none, digital, roman, super, sub, dsquare, hsquare
set -g @yukinord-tmux_pane_id_style super       # none, digital, roman, super, sub, dsquare, hsquare
set -g @yukinord-tmux_zoom_id_style none        # none, digital, roman, super, sub, dsquare, hsquare
set -g @yukinord-tmux_session_bg "on"           # on or off (transparent)
set -g @yukinord-tmux_window_center "off"       # on or off
set -g @yukinord-tmux_github_status on          # on or off

# Path widget (disabled by default)
set -g @yukinord-tmux_show_path 1
set -g @yukinord-tmux_path_format relative      # relative or full
```

## Features

- **Git Status**: Shows current branch, sync status, and change counts
- **GitHub Integration**: Displays open pull requests and issues count for the current repository
  - Pull requests (magenta)
  - Issues (red)
  - Requires GitHub CLI (`gh`) for authenticated requests or falls back to unauthenticated API calls
  - Results are cached for 5 minutes to improve performance
  - Can be disabled with `set -g @yukinord-tmux_github_status off`
- **Custom Window Numbers**: Configurable window and pane number styles
- **Path Widget**: Shows current directory path

### GitHub Integration Setup

For the best experience with GitHub integration:

1. **Install GitHub CLI**: `brew install gh` (macOS) or follow [installation instructions](https://cli.github.com/)
2. **Authenticate**: `gh auth login`
3. **Enjoy unlimited API requests** without rate limiting

Without GitHub CLI, the extension falls back to unauthenticated API requests which are rate-limited to 60 requests per hour per IP address.

## Screenshot

![yukinord-tmux](img/dark.png)
