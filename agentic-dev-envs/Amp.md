---
tags: [tool, cli-agent, proprietary, sourcegraph, spinout, enterprise]
created: 2026-05-28
---

# Amp

Sourcegraph's autonomous coding agent and the official successor to Cody. Launched May 2025 from inside Sourcegraph, spun out in December 2025 as an independent company under CEO Quinn Slack. Aimed squarely at the autonomous, repo-scale refactoring use case where IDE-resident assistants fall short.

## Origin
- Development started **February 2025** inside Sourcegraph; launched publicly **May 2025**.
- Replaces **Cody** (Sourcegraph's prior IDE assistant) — the rebrand reflects the shift from "completions in your editor" to "agent that drives the codebase."
- **Spun out as Amp Inc.** in December 2025; **Quinn Slack** (Sourcegraph co-founder) became Amp Inc. CEO.
- CLI package renamed from `@sourcegraph/amp` to `@ampcode/cli`.

## Architecture
- **Model support:** frontier-model focus — Claude (primary), GPT-5, Gemini routed under the hood. Amp does its own model selection rather than exposing a knob.
- **Surfaces:** CLI plus extensions for VS Code, Cursor, Windsurf. The CLI is treated as a peer, not a fallback.
- **Sourcegraph context:** inherits Cody's repo-graph + code-intel indexing — strongest "understands your whole monorepo" story in the cluster.
- **Multi-step planning:** explicit plan→execute→test→iterate loop; runs commands and tests inside the agent loop.
- **Team workflows:** thread-sharing, shared agent runs — collaboration is a first-class concept rather than an afterthought.
- **MCP:** supported as a client.
- **Sandboxing:** standard permission prompts; no OS-level sandbox like Codex.

## Distribution & Adoption
- License: **proprietary, closed source**.
- Install: `npm install -g @ampcode/cli`.
- No public star count — there's no open-source repo to star.
- Distribution leans on Sourcegraph's existing enterprise sales motion; less viral than Claude Code or Codex.

## Pricing
- Briefly experimented with an **ad-supported free tier** in late 2025 — ads from Axiom, Chainguard, Vanta, WorkOS appeared in the editor/CLI.
- **May 2026:** Amp Free dropped ads, capped at $10/day usage, **paused new free signups**. Existing free users grandfathered.
- Enterprise: **~$59/user/month** with team security, SAML, audit, Sourcegraph context.
- Self-serve Pro plans discontinued during 2025; current motion is contact-sales.

## Differentiators
- **Only ad-supported coding agent** ever shipped at scale (subsequently rolled back) — a genuinely novel business-model experiment.
- **Repo-graph context** from Sourcegraph's prior decade of code-intel work — no other CLI agent ships with this level of monorepo indexing.
- **Spun out into its own company** — rare for a feature inside an enterprise platform; signals Sourcegraph views the agent surface as more valuable than the search business that spawned it.
- **Replaces Cody outright** — clean cut, no dual-product confusion. Cody users were migrated rather than maintained in parallel.
- Enterprise-first when the rest of the cluster (especially Codex, Gemini CLI) chases developer mindshare first.

## See Also
- [[CLI Coding Agents]]
- [[Claude Code]]
- [[Codex CLI]]
