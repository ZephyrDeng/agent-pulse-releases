# AgentPulse

**Feel your agents' heartbeat.** A macOS menu bar app that shows what your local AI coding agents — Claude Code, Codex, Pi — are doing right now, and how much they've used.

AgentPulse runs entirely on your machine. It reads local logs, listens for hook events, and polls process state. It does not require signing in to anything, and it never sends your prompts or code anywhere.

## Download

Grab the latest signed and notarized `.dmg` from [**Releases**](https://github.com/ZephyrDeng/agent-pulse-releases/releases/latest), open it, and drag AgentPulse to Applications.

- **Requires**: macOS 14.0+, Apple Silicon
- **Updates**: built-in automatic updates via Sparkle — install once, stay current

## What it does

- **Live agent activity** — the menu bar icon and an optional side rail show whether Claude Code, Codex, or Pi are actively working, waiting on you, or idle. Driven by lifecycle hooks, a local Unix socket, and a polling fallback, so the state stays accurate even if a hook is missed.
- **Usage tracking** — per-tool token usage for Codex and Claude, including their native rate-limit windows (5h / 7d), with a burn-rate estimate that warns you before you hit a reset.
- **35-day usage heatmap** — a daily token heatmap with hover previews and a click-through detail view broken down by source and model.
- **Desktop notifications that jump back** — agent completion and permission-request notifications return you straight to the originating terminal tab or window (iTerm2, Terminal.app, Ghostty, Warp, VS Code, JetBrains, tmux).
- **User-defined hooks** — run your own shell commands on agent lifecycle events, quota changes, or app lifecycle events, with the event payload passed via environment variables.
- **Built-in read-only MCP server** — exposes `get_changelog` and `get_hooks` over Streamable HTTP on `127.0.0.1`, so your agents can introspect what changed and where their hook configuration lives. No network exposure, no write access.
- **Side rail** — a slim, collapsible trigger docked to the screen edge mirroring the menu panel, for persistent visibility without keeping the menu open.

## Privacy

Everything stays local. AgentPulse reads agent session logs and credentials files on your machine to compute usage; nothing is uploaded, and there is no telemetry. The only network traffic the app initiates is the Sparkle update check against this repository.

## Feedback

Bug reports and feature requests are welcome in [Issues](https://github.com/ZephyrDeng/agent-pulse-releases/issues).

## About this repository

This repository hosts AgentPulse's public releases: the downloadable artifacts, the Sparkle update feed (`appcast.xml`), and release notes. AgentPulse is distributed as a free, closed-source binary; the source code is not published here.
