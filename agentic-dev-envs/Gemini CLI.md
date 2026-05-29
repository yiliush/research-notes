---
tags: [tool, cli-agent, open-source, apache-2, google, sunset-warning]
created: 2026-05-28
---

# Gemini CLI

Google's open-source terminal agent for Gemini — the most-starred CLI agent on GitHub, the most generous free tier in the cluster, and the only one with an announced sunset date for individual users. Launched in June 2025 to compete with Claude Code and Codex; being replaced by Antigravity CLI for non-enterprise tiers in June 2026.

## Origin
- Launched **June 25, 2025** by Google as an open-source TypeScript/Node CLI.
- Built by the Google Gemini team; community-driven via GitHub (6,000+ accepted contributions in its first year).
- Release cadence: weekly stable (Tuesdays), weekly preview, daily nightly.

## Architecture
- **Model support:** Gemini family — Gemini 3 by 2026 with a **1M token context window**.
- **Built-in tools:** Google Search grounding (unique to Google), file operations, shell commands, web fetch.
- **MCP:** full client support for custom tool integrations.
- **Memory:** project memory file convention (`GEMINI.md`), mirroring `CLAUDE.md`.
- **Auth:** personal Google account (free tier), Google AI Pro/Ultra subscription, or Google Cloud / Vertex AI for enterprise.
- **Sandboxing:** permission prompts; optional containerized sandbox via `--sandbox`.

## Distribution & Adoption
- License: **Apache 2.0**, fully open source.
- Install: `npm install -g @google/gemini-cli` (Node 20+ required), `npx @google/gemini-cli` for one-off, Homebrew, MacPorts.
- GitHub stars: **~105K** on `google-gemini/gemini-cli` (May 2026) — **most-starred CLI agent in the cluster.**
- Community pace: 6,000+ accepted PRs in ~11 months.

## Pricing
- **Free tier** (personal Google account): **60 requests/min, 1,000 requests/day** — by far the most generous free quota in the cluster.
- Google AI Pro / Ultra subscriptions raise limits.
- Enterprise via Gemini Code Assist / Vertex AI.
- **Sunset warning:** Google announced that on **June 18, 2026**, free users, AI Pro/Ultra subscribers, and individual Code Assist users will stop being served. Non-enterprise users will be pushed to **Antigravity CLI**. The OSS repo accepted 6,000 contributions before this enterprise-only pivot — a controversial move covered widely in tech press May 2026.

## Differentiators
- **Highest star count in the cluster** (~105K) — partly free-tier marketing, partly Google's brand pull.
- **1M token context** — biggest window of any agent here, useful for whole-codebase reasoning passes.
- **Google Search grounding** built in — no other CLI agent ships first-party web grounding.
- **Most generous free tier** — 1,000 daily requests with no card on file is unmatched.
- **Sunset risk** — the only entry in the cluster with an announced end-of-life date for individuals. Long-term viability for non-enterprise users is openly uncertain.
- Apache 2.0 license means even after sunset, the codebase is forkable — but Google's hosted backend is what made the free tier work.

## See Also
- [[CLI Coding Agents]]
- [[Claude Code]]
- [[Codex CLI]]
