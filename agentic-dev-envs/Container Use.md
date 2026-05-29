---
tags: [tool, parallel-orchestrator, containers, dagger, oss, apache-2, mcp]
created: 2026-05-28
---

# Container Use

Dagger's entry into the parallel-agent space, and the only major one that swaps git worktrees for full container isolation. Container Use lets multiple coding agents run safely in parallel by giving each one a fresh container on its own branch — solving a different problem than [[Claude Squad]] / [[Conductor]] (which assume the host filesystem is the unit of isolation).

## Origin
- Repo: `dagger/container-use`.
- Maintained by **Dagger**, the company behind the Dagger programmable CI/CD engine (Solomon Hykes's post-Docker venture).
- Released mid-2025; positioned by Dagger as "Containing Agent Chaos" in their launch blog.
- License: **Apache-2.0**.
- Primary language: Go (~97%).

## Architecture
- An **MCP server** that exposes containerized environments as a tool surface to any MCP-compatible coding agent.
- Each agent or task gets a fresh container, launched and managed via Dagger under the hood.
- Each container is tied to its own **git branch** — work product flows back through standard git review.
- Real-time visibility: full command history and logs per agent.
- Operators can drop into any agent's terminal for direct intervention.
- Compatible with Claude Code, Cursor, and other MCP-aware agents — Container Use does not replace the agent, it provides the sandbox.

## Distribution & Adoption
- Install: Homebrew on macOS or a universal install script.
- Requires Docker + Git locally.
- GitHub stars: **~3.8K** as of May 2026 — second only to [[Claude Squad]] in the cluster.
- Latest release: `v0.4.2` (August 19, 2025); project still labeled "experimental/early."
- 192 forks, growing Discord community.

## Pricing
- Free, OSS. Dagger's commercial model lives in the Dagger Engine / Dagger Cloud, not in Container Use.

## Differentiators
- **Container isolation** vs. worktree isolation — the only major cluster entrant that takes this approach. Stronger blast-radius containment, at the cost of higher per-agent startup overhead and Docker as a hard dependency.
- **MCP-native** delivery — Container Use is installed as an MCP server, which means any new MCP-compatible agent gets containerized sandboxes for free.
- Strategic alignment with Dagger's broader thesis: programmable, reproducible environments as a primitive — applied to AI agents instead of CI runs.
- Best fit when the agents being run are partially trusted (e.g., autonomous overnight sweeps) and the host environment matters (system packages, credentials).

## See Also
- [[Parallel Agent Orchestrators]] — cluster index
- [[Claude Squad]] — worktree-isolated counterpart
- [[uzi]] — explicit worktree-vs-container contrast in its README
- [[VibeKit]] — also a sandbox-first parallel runner
- [[Model Context Protocol (MCP)]]
