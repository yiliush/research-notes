---
tags: [tool, parallel-orchestrator, go, oss, mit, devflowinc, tmux]
created: 2026-05-28
---

# uzi

A Go CLI for spinning up many coding agents in parallel git worktrees, built by the Trieve team as a side project to their main search-infrastructure business. uzi sits squarely in the same architectural lane as [[Claude Squad]] — Go + tmux + worktrees — but trades the polished TUI for a simpler scriptable CLI surface.

## Origin
- Repo: `devflowinc/uzi`.
- Built by **Devflow, Inc.**, the company behind **Trieve** (YC W24 — all-in-one search/RAG/recommendations API).
- Devflow founders: **Denzell Ford** and **Nick Khami** (the same pair who built Trieve).
- uzi is an internal-dogfooding tool that was open-sourced rather than the company's main product.
- License: **MIT**.
- Primary language: Go (~75%).

## Architecture
- CLI tool installed via `go install github.com/devflowinc/uzi@latest`.
- Each agent gets:
  - Its own **git worktree** on a dedicated branch
  - Its own **tmux session**
  - Its own **dev-server port** drawn from a configurable range
- Configured via a `uzi.yaml` in the project root: `devCommand` (how to start the dev server) and `portRange` (which ports uzi may allocate).
- Per-agent dependency installation, so each worktree can have its own `node_modules` / `venv` without colliding.
- **Checkpoint command** merges a chosen agent's branch back to main in one step.
- Agent-agnostic: works with Claude Code, Codex, Cursor CLI, Aider, etc.

## Distribution & Adoption
- Install via Go toolchain only; no Homebrew formula as of May 2026.
- Prerequisites: `git`, `tmux`, Go, and whichever agent CLI(s) the user runs.
- GitHub stars: **~579** as of May 2026.
- Latest release: `v0.0.2` (June 3, 2025) — the project remains pre-1.0 and lightly maintained.

## Pricing
- Free, OSS. No commercial layer.

## Differentiators
- Built and shipped by a YC-funded company (Devflow/Trieve) as a side artifact, not as a venture — which keeps it small, focused, and unburdened by monetization pressure.
- Explicit handling of per-agent dev servers + port management is unusual in the cluster — most competitors leave port collisions to the user.
- Closer to a Unix-style tool than a TUI: scriptable, composable, no interactive UI required.
- Monorepo-friendly via worktrees specifically (the README contrasts this with container-based approaches like [[Container Use]]).

## See Also
- [[Parallel Agent Orchestrators]] — cluster index
- [[Claude Squad]] — TUI competitor in the same language
- [[Container Use]] — container-isolated alternative
- [[Agent Farm]]
- [[Claude Code]]
