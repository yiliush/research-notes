---
tags: [tool, task-queue, agent-orchestration, oss, mit, markdown, spec-driven]
created: 2026-05-28
---

# Backlog.md

A markdown-native project board that has become a de facto task feeder for parallel coding agents. Backlog.md is not itself an orchestrator in the [[Claude Squad]] / [[Conductor]] sense — it doesn't spawn agents — but its design assumption that each task maps to one agent session has made it the most common "what should the agents work on next?" layer above the orchestrators in this cluster.

## Origin
- Repo: `MrLesk/Backlog.md`.
- Author: **MrLesk** (GitHub handle); developed actively through 2025–2026 with an open contributor community.
- License: **MIT**.
- Primary language: TypeScript (~87%).
- GitHub stars: **~5.6K** as of May 2026 — high for a tooling project of this shape.
- 888 commits, 185 releases; latest `v1.45.1` on May 7, 2026 — heavy release cadence.

## Architecture
- Turns any folder with a git repo into a **self-contained project board** powered by plain Markdown files.
- Zero-config CLI (`backlog task create`, `backlog task edit`, `backlog search`).
- Terminal Kanban board + web UI with drag-and-drop.
- **MCP server** built in — directly callable by Claude Code, Codex, Gemini CLI, Kiro.
- Definition-of-Done checklist templates encourage tasks small enough for one agent session.
- Fuzzy search across tasks, docs, decisions.
- 100% offline; all state lives in git.
- VS Code extension with issues panel, kanban view, and inline editing.

## How it Fits the Parallel-Orchestrator Cluster
- The common pattern by mid-2026: **Backlog.md holds the task queue**, an orchestrator ([[Claude Squad]], [[Conductor]], or [[uzi]]) **claims tasks** and assigns each to a worktree-isolated agent.
- The "one task = one PR = one agent session" discipline that Backlog.md enforces is exactly the granularity the parallel orchestrators need to keep agents from stepping on each other.
- Backlog.md is also the closest project in this cluster to the **TASKS.md** spec (a related lightweight standard for agent task queues, companion to AGENTS.md).

## Pricing
- Free, OSS. No commercial offering.

## Differentiators
- **Markdown-native, git-native, offline-first** — every other entrant in the cluster requires a daemon or GUI; Backlog.md is "just files."
- **MCP-first** integration with agents — no shim needed.
- Spec-driven philosophy: the project's pitch is that good task decomposition is what makes parallel agents work, and that this decomposition belongs in the repo next to the code.
- Adjacent OSS projects in this niche: **TASKS.md** (the lightweight spec), **Backlog (backlog.so)** (a separately-developed commercial-ish task orchestrator with the same name idea), **fuel** (ashleyhindle/fuel) — collectively a small but growing sub-cluster.

## See Also
- [[Parallel Agent Orchestrators]] — cluster index
- [[Claude Squad]] — common pairing
- [[Conductor]]
- [[Claude Code]]
- [[Model Context Protocol (MCP)]]
