# New mcp release

# 📦 Latest MCP — v1.3.0

Adds `discover_marketplace` + `recommend_marketplace`

**Release page:** https://github.com/Aniket-think41/skillshare-mcp/releases/tag/v1.3.0

## Direct downloads

The latest URLs always point to the newest release.

| Platform | Command |
|---|---|
| Linux | `curl -L https://github.com/Aniket-think41/skillshare-mcp/releases/latest/download/skillshare-mcp-linux-amd64 -o skillshare-mcp` |
| macOS (Apple Silicon) | `curl -L https://github.com/Aniket-think41/skillshare-mcp/releases/latest/download/skillshare-mcp-macos-arm64 -o skillshare-mcp` |
| Windows | `skillshare-mcp-windows-amd64.exe` |

## Install (macOS/Linux)

Then register with Claude Code:

```bash
chmod +x skillshare-mcp && sudo mv skillshare-mcp /usr/local/bin/skillshare-mcp

claude mcp add skillshare \
  --env SKILLSHARE_API_URL=https://skillshare-backend-1081098542602.us-central1.run.app \
  -- skillshare-mcp
```

Then in Claude Code just say **"log in to skillshare"** — it runs the login tool and gives you a browser link + code.

## 📊 Status-line — the one-time "enable once" step

The install/push counts in Claude Code's status bar are wired via a one-time command. Two ways:

### A) If you have the CLI

Latest is v1.2.1 — https://github.com/Aniket-think41/skillshare-cli/releases/latest

```bash
skillshare setup-statusline
```

- Writes to `~/.claude/settings.json` (add `--project` for `./.claude/settings.json`)
- `--remove` to turn it off
- `--force` to replace an existing different status line
- `--print` to preview the command without changing anything

Restart/reload Claude Code afterward to see it. Counts then refresh automatically.

### B) MCP-only (no CLI installed)

Right after you log in, the MCP offers to enable it — just say **"yes, enable the status bar"** and it calls the `setup_statusline` tool (same effect, edits your `settings.json`). It only does this once you approve.

### Quick CLI install for reference (macOS/Linux)

```bash
curl -L https://github.com/Aniket-think41/skillshare-cli/releases/latest/download/skillshare-linux-amd64 -o skillshare
chmod +x skillshare && sudo mv skillshare /usr/local/bin/skillshare
skillshare login          # browser sign-in
skillshare setup-statusline
```
 ┌─────────────────────────────┬─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┐
  │           Command           │                                                                What you get                                                                 │
  ├─────────────────────────────┼─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┤
  │ skillshare inbox            │ Lists your notifications (resources added/published in your orgs/projects/pods). --unread for only new, --mark-read to clear.               │
  ├─────────────────────────────┼─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┤
  │ skillshare panel            │ Opens the clickable install panel (Tkinter GUI) — expandable rows, one-click install.                                                       │
  ├─────────────────────────────┼─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┤
  │ skillshare watch            │ Background watcher — pops desktop toast notifications for new inbox items (and local skills worth sharing). --interval 60, --once for cron. │
  ├─────────────────────────────┼─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┤
  │ skillshare setup-statusline │ One-time: shows your install/push counts in Claude Code's status bar.                                                                       │
  └─────────────────────────────┴─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┘


