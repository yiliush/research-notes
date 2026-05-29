---
tags: [tool, parallel-orchestrator, tui, oss, agpl, tmux]
created: 2026-05-28
---

# Claude Squad

The dominant open-source terminal orchestrator for running multiple coding agents in parallel. Claude Squad is the OSS counterweight to [[Conductor]]: same git-worktree-per-agent pattern, but delivered as a Go TUI sitting on top of tmux rather than a Mac app. By mid-2026 it is the most-starred project in the parallel-orchestrator cluster.

## Origin
- Repo: `smtg-ai/claude-squad`.
- Released mid-2025; reached ~7.7K GitHub stars by May 2026.
- License: **AGPL-3.0** — notably more restrictive than the MIT defaults across the rest of the cluster.
- Primary language: Go (~90%). Binary installs as the `cs` command.

## Architecture
- TUI written in Go (bubbletea-style).
- **tmux** provides session isolation per agent — each agent's terminal lives in its own tmux session that persists even after the TUI is closed.
- **git worktrees** provide filesystem isolation — each session works on its own branch in its own directory.
- Agents are configurable: Claude Code, Codex, Gemini, Aider, OpenCode, Amp — anything that runs as a CLI process.
- Pre-commit diff review: the TUI surfaces a diff view before changes get committed/pushed.
- Background auto-accept mode for agents that have been validated to run unattended.
- Config lives at `~/.claude-squad/config.json`; supports multiple named profiles.

## Distribution & Adoption
- Install: `brew install claude-squad` (most common) or `curl | bash` script.
- Prerequisites: `tmux` and `gh` (GitHub CLI).
- GitHub stars: **~7.7K** as of May 2026.
- The MCP marketplaces and "best parallel orchestrators of 2026" blog roundups consistently rank Claude Squad as the leading OSS option.

## Pricing
- Free, OSS. AGPL-3.0 license means downstream SaaS-style wrapping triggers copyleft obligations — relevant for any company considering forking it into a hosted product.

## Differentiators
- Terminal-native — runs over SSH, fits into a tmux-heavy workflow, no GUI dependency.
- Multi-agent support out of the box (not just Claude Code) — broader than Conductor's Claude+Codex.
- AGPL is a deliberate strategic choice: prevents the obvious "hosted Claude Squad SaaS" play that a permissive license would invite.
- Persists agent work via tmux even when the TUI is closed — closer to a background daemon than a session-bound app.

## See Also
- [[Parallel Agent Orchestrators]] — cluster index
- [[Conductor]] — the GUI counterpart
- [[uzi]] — similar Go+tmux+worktree shape, smaller
- [[Agent Farm]] — bash-style orchestrator for higher agent counts
- [[Claude Code]]
