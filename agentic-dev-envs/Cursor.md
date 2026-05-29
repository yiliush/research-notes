---
tags: [company, ai-ide, cursor, anysphere, ade-cluster]
created: 2026-05-28
---

# Cursor

Cursor, made by Anysphere, is the defining AI-native IDE of the current generation — a VS Code fork that, by early 2026, became the fastest B2B SaaS company in history to reach $2B ARR and the highest-valued AI coding startup ever, sitting at the center of the AI development environment market. It set the template (Tab autocomplete, Composer multi-file edits, Agent mode) that every other entrant in this cluster now copies or differentiates against.

## Company
- Founded 2022 by Michael Truell, Sualeh Asif, Arvid Lunnemark, and Aman Sanger — all MIT students at incorporation. HQ: San Francisco. Operates as Anysphere, Inc. (DBA Cursor).
- Truell is CEO; founders are in their early-to-mid twenties. Asif (Karachi, IMO competitor) and Lunnemark (former Math Olympiad medalist) handle research/infra; Truell and Sanger were Neo Scholars.
- Funding rounds (verified May 2026):
  - Seed, Oct 2023: $8M led by OpenAI Startup Fund; angels Nat Friedman, Arash Ferdowsi
  - Series A, Aug 2024: ~$60M led by Andreessen Horowitz at ~$400M
  - Series B, Dec 2024: $105M led by Thrive Capital at $2.5B
  - Series C, May 2025: $900M led by Thrive Capital at $9.9B
  - Series D, Nov 2025: $2.3B at $29.3B post-money
  - In talks Apr/May 2026: ~$2B at ~$50B pre-money, co-led by a16z and Thrive Capital, Nvidia participating as strategic investor (per TechFundingNews, TheNextWeb)
- Headcount: unclear and disputed — PitchBook lists ~400, JobsByCulture estimates 50–300, with ~84 open roles as of April 2026. Famously lean for the valuation.

## Product
- Editor architecture: VS Code fork with proprietary AI layer. Custom indexing and inference infrastructure run server-side; client is a thin AI shell.
- Indexing/retrieval: embeddings-based codebase index built at workspace open; updated continuously. Retrieval-augmented for chat and Composer. Privacy mode keeps embeddings local-only.
- Model routing: multi-provider (Anthropic Claude Sonnet/Opus, OpenAI GPT-5, Google Gemini, xAI Grok) plus in-house models. Users pick a model per request; "Auto" mode routes based on task.
- In-house models: Composer-1 launched Oct 2025 alongside Cursor 2.0 — a mixture-of-experts model RL-trained on real software engineering tasks. Marketed as 4x faster than comparable frontier models with most agent turns under 30 seconds. Composer-2 released later with frontier-level coding capability at fractional cost.
- Key features: Tab autocomplete (the original differentiator), Cmd-K inline edit, Chat, Composer (multi-file edit with diff preview), Agent mode (autonomous task execution with tool use), Background Agents (long-running cloud tasks), MCP integration, Bugbot (PR review).
- Cursor 2.0 (Oct 2025) introduced multi-agent architecture: run multiple agents in parallel on the same project, each in its own sandbox.

## Pricing
Current tiers as of May 2026:
- Hobby: Free — limited Agent requests, limited Tab completions
- Pro: $20/month — unlimited Tab, $20 monthly usage credits, full Agent and Composer access
- Pro+: $60/month — 3x usage credits
- Ultra: $200/month — 20x usage multiplier, priority access to new features and frontier models
- Teams (Business): $40/user/month — admin controls, SSO, pooled credits
- Enterprise: custom pricing — SOC 2, audit logs, custom retention
- 20% discount for annual billing on all paid tiers.

## Traction
- ARR trajectory (verified via Sacra, TechCrunch, Latka):
  - Jan 2025: $100M
  - Jun 2025: $500M
  - Late 2025: $1B (at Series D)
  - Feb 2026: $2B — fastest B2B 0→$2B in history (~3 years)
  - Forecast: $6B+ ARR by EOY 2026
- Customers: 64% of Fortune 500 reported on cursor.com/enterprise; named: OpenAI, Stripe, Shopify, Uber, Adobe, Spotify, Midjourney, Nvidia, Salesforce, PwC
- Scale: 50,000+ enterprise teams; 100M+ lines of enterprise code written/day
- Enterprise share: ~60% of revenue
- Total funding to date: over $10B raised since founding (pending May 2026 round close)

## Strategic Position
- Category leader by a wide margin in revenue and valuation. Moat is the combination of (a) the index/inference stack that Composer plugs into, (b) a brand among engineers that no other entrant has matched, and (c) Fortune 500 enterprise distribution acquired during 2024–2025 ahead of competitors.
- Threats: Windsurf/Cognition has rebounded post-acquisition with SWE-1.5 and Codemaps and is the only entity matching Cursor on Power Rankings. GitHub Copilot is still the default-on-corporate-laptop incumbent. Anthropic's Claude Code and OpenAI's Codex CLI are squeezing from the model-vendor side — they have model economics Cursor doesn't, though Composer is meant to fix this.
- The Composer thesis (own the model + the runtime) is the bet against the "wrapper" critique. As of May 2026 Composer is good enough for routine agentic work but not frontier — Cursor still routes high-difficulty tasks to Claude Sonnet 4.5 / GPT-5.

## See Also
- [[Windsurf]] — #2 competitor, now part of Cognition
- [[Zed]] — performance-focused alternative
- [[Replit]] — adjacent in cloud-IDE / vibe-coding territory
- [[Trae]] — Chinese state-adjacent alternative
- [[AI-Native IDEs]] — cluster index
- [[Codebase Indexing]]
- [[Agent Harness]]
- [[Market Landscape]]
