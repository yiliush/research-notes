---
tags: [company, ai-ide, replit, cloud-ide, vibe-coding, ade-cluster]
created: 2026-05-28
---

# Replit

Replit is the browser-native AI IDE — the only entrant in this cluster that runs entirely in the cloud and targets non-developers (vibe-coders, product managers, founders) as much as professional engineers. After a near-death restructure in early 2024 (~50% staff cut), Replit pivoted hard around the Replit Agent and rebuilt itself into one of the fastest-growing AI companies of the cycle: from $2.8M ARR in January 2025 to a $9B valuation in March 2026. It sits at the intersection of AI-IDE and natural-language app-builder categories.

## Company
- Founded 2016 by Amjad Masad (CEO), Faris Masad, and Haya Odeh. HQ: San Francisco.
- Masad was previously an early engineer at Facebook (React Native team).
- Backed by Y Combinator — invested in Seed round Oct 22, 2018 after Paul Graham discovered the project on Hacker News and personally championed it.
- Funding rounds (verified May 2026):
  - Seed (2018) — YC
  - Series A (2020), Series B (2021)
  - 2023: ~$100M at $1.16B post-money
  - Sep 2025: $250M Series led by Prysm Capital at $3B
  - Mar 2026: $400M Series D led by Georgian at $9B — 3x in six months. Participants: G Squared, Prysm, 1789 Capital, YC, Coatue, a16z, Craft Ventures, Qatar Investment Authority. Strategic: Accenture Ventures, Databricks Ventures, Okta Ventures, Tether.
- Total funding to date: ~$922M across 8 rounds and 45 investors
- 2024 restructure: ~50% staff layoff, refocus around Agent. The pivot worked — ARR went from $2.8M (Jan 2025) → $150M (Sep 2025) → tracking toward $1B run-rate by EOY 2026.
- Masad became a billionaire on the March 2026 round (Forbes-estimated $2B net worth)

## Product
- Architecture: full browser-based IDE backed by cloud sandboxes (Replit's container/VM infrastructure). Every project is also a deployable app — Replit hosts, runs, and serves it.
- Distinctively for this cluster: editor is not the moat — the runtime is. Replit owns build, deploy, hosting, databases (ReplitDB), object storage, and now mobile app distribution.
- Replit Agent timeline:
  - Sep 2024: Agent v1 — natural-language project creation
  - Feb 2025: Agent v2 — greater autonomy
  - 2025: Agent v3 — longer autonomous task chains
  - Mar 2026: Agent 4 (web) — parallel agents on a single project, design-canvas interface, multi-output (web apps, mobile apps, slide decks, data apps, animations). Replit claims 10x faster ship velocity vs Agent 3.
  - May 2026: Agent 4 on iPhone, following a 4-month App Store review dispute with Apple
- Model routing: multi-provider — Claude (primary), GPT, Gemini. Replit handles model selection on the user's behalf inside Agent.
- Indexing/retrieval: less central than for Cursor — Agent works from project state and orchestrates code generation + execution feedback loops, leveraging the controlled cloud sandbox to verify each step.
- Earlier product: Ghostwriter (autocomplete + chat, 2022–2024) — largely sunset / subsumed into Agent.

## Pricing
Current tiers as of May 2026:
- Starter: Free — limited Agent capability, daily AI credits, 1 published app
- Core: $25/month ($20/mo billed annually) — Agent access, $25 monthly usage credits, up to 5 collaborators, autonomous long builds, unlimited workspaces
- Pro: $95/month (billed annually, flat fee, replaces older Teams tier as of Feb 24, 2026) — up to 15 builders, pooled credits with tiered discounts, limited credit rollover, collaborative workspaces, priority support
- Enterprise: custom

## Traction
- ARR: $2.8M (Jan 2025) → $150M (Sep 2025) → tracking $1B run-rate by EOY 2026 (per Sacra and company statements)
- User base in tens of millions of registered users (legacy IDE), with the Agent monetization layer being the recent driver
- Customer mix: heavy small-business and prosumer; growing enterprise via the new Pro tier and Databricks/Accenture partnerships
- Notable: Replit is consistently cited (alongside Lovable, Bolt) as the canonical "vibe-coding" platform — the term itself crystallized in late 2024/2025 around these products

## Strategic Position
- Wildly different positioning from Cursor/Windsurf/Zed. Replit is selling "ship a working app, hosted, today" rather than "make engineers faster." The user is often not an engineer at all.
- Vertical integration is the moat: agent + runtime + hosting + storage + distribution (mobile/web). Cursor cannot ship a deployed app at the end of an agent run; Replit can.
- Competitive pressure: Lovable, Bolt.new, v0 (Vercel), and now Cursor-with-deployments and Windsurf-with-Devin are all attacking the "natural-language to deployed app" wedge. Replit's defense is the longer-standing platform infrastructure and the consumer/prosumer brand.
- Risk: as frontier models commoditize code generation, the question is whether Replit's runtime+hosting layer is enough of a moat or whether it gets disintermediated. The aggressive iPhone push (Agent 4 on mobile) is a bet on owning a non-laptop creator surface.

## See Also
- [[Cursor]]
- [[Windsurf]]
- [[Zed]]
- [[Trae]]
- [[AI-Native IDEs]]
- [[Vibe Coding]]
- [[Agent Harness]]
- [[Market Landscape]]
