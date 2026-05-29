---
tags: [tool, parallel-orchestrator, sandbox, oss, mit, superagent, docker]
created: 2026-05-28
---

# VibeKit

A sandbox-first runner for coding agents from Superagent Technologies. VibeKit's primary pitch is safety — running [[Claude Code]], Codex, Gemini, or Grok output in isolated Docker containers with automatic secret redaction — but it ships enough git-worktree and multi-agent plumbing that it functions as a parallel orchestrator at the edge of this cluster.

## Origin
- Repo: `superagent-ai/vibekit`.
- Built by **Superagent Technologies Inc.** — the team behind Superagent (the broader AI-agent platform / red-team testing product at superagent.sh).
- Released 2025; positioned in launch posts as "VibeKit CLI."
- License: **MIT**.
- Primary language: TypeScript (~80%).

## Architecture
- Wraps any coding agent CLI and runs its output inside an **isolated Docker container** per session.
- **Secret redaction layer**: scans `.env` files, API keys, and credentials before any agent input crosses the network boundary to the LLM.
- **Observability**: live logs, traces, and metrics per agent.
- **Git worktree integration**: supports running parallel branches in their own worktrees — the parallel-orchestrator surface — but framed as a supporting feature, not the headline.
- Companion packages:
  - **VibeKit SDK** — embed VibeKit's sandboxed-agent runtime in other applications.
  - **VibeKit Auth** — auth handling for VibeKit-powered apps.
- Recent (2026) work on **Dagger Local Sandboxes** integration — overlapping with [[Container Use]] territory.

## Distribution & Adoption
- Install via npm (CLI) plus Docker as a runtime prerequisite.
- GitHub stars: **~1.8K** as of May 2026.
- 661 commits in a monorepo containing CLI, SDKs, docs, and tests.
- Active development through 2026.

## Pricing
- Free, OSS. Superagent's commercial offering is the broader hosted Superagent platform / Red Team Testing product, not VibeKit itself.

## Differentiators
- **Security-first framing** rather than productivity-first — the wedge is "I don't want my agent leaking secrets or trashing my machine" rather than "I want to run 8 agents at once."
- **SDK shape**: VibeKit is the only cluster entrant aggressively positioned as embeddable infrastructure for other people's products.
- Overlaps with [[Container Use]] on container-sandbox semantics, but goes further on secret redaction and is TypeScript- rather than Go-shaped.
- Useful as a parallel orchestrator only insofar as you also want the safety layer — pure "I trust my agents" workflows tend to skip the Docker overhead and use [[Claude Squad]] or [[uzi]] instead.

## See Also
- [[Parallel Agent Orchestrators]] — cluster index
- [[Container Use]] — closest peer on container isolation
- [[Claude Squad]] — simpler, worktree-only alternative
- [[Claude Code]]
