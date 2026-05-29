---
tags: [tool, parallel-orchestrator, mac-app, yc, melty-labs, proprietary]
created: 2026-05-28
---

# Conductor

The Mac-native flagship of the parallel-agent-orchestrator cluster. Conductor turns a developer's laptop into a control panel for a team of [[Claude Code]] and [[Codex CLI]] agents running side-by-side in isolated git worktrees, each with its own chat, terminal, preview, and diff viewer. As of May 2026 it is the highest-funded entrant in the category and the one most visibly used inside other YC-backed startups.

## Origin
- Built by **Melty Labs**, the same team behind the earlier Melty editor.
- Founders: **Charlie Holtz** (CEO, ex-Replicate) and **Jackson de Campos**.
- YC batch: **Summer 2024** (S24). Headquartered in San Francisco.
- Conductor launched publicly in 2025; the company pivoted from the Melty editor to Conductor when parallel-agent UX became the clearer wedge.
- Funding: **$22M Series A** co-led by Spark Capital and Matrix Partners (announced early 2026).
- Reported 10× growth between January 2026 and May 2026.

## Architecture
- Native macOS application (not Electron in the way Crystal was) — entire stack runs locally on the user's Mac.
- Each agent runs in its own **git worktree** with a dedicated branch, scoped chat thread, terminal, preview pane, and diff viewer.
- Spawns underlying CLI agents as subprocesses: officially supports Claude Code and Codex.
- Reuses the user's existing Claude Pro / Max subscription or API key for inference — Conductor itself does not broker model access.
- Diff-first review UX: the differentiator vs. Claude Squad is that diffs are surfaced as the primary unit of switching between agents, not terminal sessions.
- Recent additions (per the company): **Conductor Cloud** for running the same orchestration off-device, and an **Enterprise** tier.

## Distribution & Adoption
- License: proprietary, closed-source, free download.
- Install: direct `.dmg` from conductor.build.
- Current version on the public download: 0.59.x as of May 2026.
- Reported user base: engineers at Google, Meta, Stripe, Datadog, Block, Ramp, Intercom, HubSpot, Chime, and (per Holtz's own posts) Linear, Vercel, Notion, Supabase.

## Pricing
- Free for individual download as of May 2026.
- Conductor Cloud and Enterprise tiers exist but pricing is not posted publicly — "contact us" gated.
- The monetization thesis is team seats + cloud runtime, not the local Mac app itself.

## Differentiators
- The only entrant in this cluster with a native Mac app and serious VC backing.
- Diff-as-primary-pane UX — most other tools (Claude Squad, uzi) make you tab through terminal sessions.
- "Dogfood at scale" story: the team builds Conductor using Conductor, which Holtz cites frequently.
- Free distribution despite VC funding — keeps it adjacent to the OSS competitors on adoption friction, then monetizes on Cloud + Enterprise.

## See Also
- [[Parallel Agent Orchestrators]] — cluster index
- [[Claude Squad]] — terminal-native OSS counterpart
- [[Crystal]] — the earlier Electron version of the same idea
- [[Claude Code]]
- [[Codex CLI]]
