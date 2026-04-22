# Claude Code Status Bar

A rich, single-line status bar for [Claude Code](https://claude.ai/code) that shows everything you need at a glance.

```
opus 4.6 on main  ●●●●○○○○○○○○○○○○ 25%  $0.42  ↑12k ↓3k  +45 -12  - ●●●●●●●○○○○○○○○○ 45%/12% - duration: 14m
```

## What it shows

| Segment | Example | Description |
|---------|---------|-------------|
| **Model** | `opus 4.6` | Current model, lowercase |
| **Branch** | `on main` | Git branch (hidden if not in a repo) |
| **Context** | `●●●●○○○○ 25%` | Context window usage dot gauge |
| **Cost** | `$0.42` | Session cost — green < $50, yellow $50-100, red > $100 |
| **Tokens** | `↑12k ↓3k` | Cumulative input/output tokens |
| **Lines** | `+45 -12` | Lines added/removed |
| **Usage** | `●●●●●●●○○○○○○○○○ 45%/12%` | 5-hour / 7-day rate limit (Pro/Max only) |
| **Duration** | `duration: 14m` | Session wall-clock time |
| **Agent** | `reviewer` | Agent name (hidden if not using `--agent`) |

## Install

```bash
curl -fsSL https://raw.githubusercontent.com/MateoSegura/claude-status-install.sh/main/install.sh | bash
```

Requires `jq` — install with `brew install jq` or `apt install jq`.

## What it does

1. Writes the status line script to `~/.claude/scripts/statusline-command.sh`
2. Adds `statusLine` config to `~/.claude/settings.json` (skips if already set)

Restart Claude Code after installing.

## Uninstall

```bash
rm ~/.claude/scripts/statusline-command.sh
```

Then remove the `"statusLine"` block from `~/.claude/settings.json`.
