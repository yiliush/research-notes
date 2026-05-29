---
tags: [company, ai-ide, windsurf, cognition, ade-cluster, m-and-a-saga]
created: 2026-05-28
---

# Windsurf

Windsurf is the AI-native IDE that survived a 72-hour corporate dismemberment in July 2025 and emerged stronger inside Cognition AI. Originally built by Codeium as a Cascade-driven Cursor competitor, the company was carved up by Google (reverse-acquihire of CEO Varun Mohan and core researchers for $2.4B) and then immediately acquired in its entirety by Cognition. As of mid-2026 it sits at #1 on the LogRocket AI Dev Tool Power Rankings, ahead of both Cursor and Copilot, powered by Cognition's SWE-1.5 model and Codemaps.

## Company
- Original founders: Varun Mohan (CEO) and Douglas Chen, co-founded Exafunction in 2021, which later became Codeium and then rebranded the IDE product to Windsurf in Nov 2024. HQ originally Mountain View.
- Funding history pre-saga:
  - Series A 2022, Series B 2023 led by Greenoaks
  - Series C, Aug 2024: $150M at $1.25B valuation, led by General Catalyst
  - $250M Series at $2.85B in early 2025
- The Windsurf Saga (verified via CNBC, TechCrunch, Cognition blog):
  - Apr 2025: OpenAI in talks to acquire Windsurf for $3B; exclusivity expires without close
  - Jul 11, 2025: Google announces non-acquisition reverse-acquihire — pays $2.4B for a non-exclusive license to Windsurf tech and pulls Varun Mohan, Douglas Chen, and key researchers into Google DeepMind to work on Gemini agentic coding
  - Jul 11, 5pm: Cognition CEO Scott Wu opens first call about acquiring the remaining company
  - Jul 14, 2025: Cognition announces definitive agreement to acquire Windsurf entirely — IP, product, trademark, brand, and ~210 remaining employees. Acquisition price reported at ~$250M (per NxCode and others).
  - All Windsurf employees got accelerated vesting, waived cliffs, and financial participation per Cognition's blog.
- Current parent: Cognition AI. Scott Wu is CEO; Jeff Wang heads Windsurf operations. Cognition itself raised $400M at $10.2B in Sep 2025 and $1B at $26B post-money on May 27, 2026 (Lux/General Catalyst/8VC led).

## Product
- Editor architecture: VS Code fork — same baseline as Cursor — with proprietary AI runtime. Now tightly integrated with Cognition's Devin infrastructure.
- Indexing/retrieval: "Fast Context" — proprietary retrieval system co-designed with the SWE-1.5 model rather than generic RAG. Continuously updated codebase graph.
- Agent harness — Cascade: agentic mode that reads codebase, plans, calls tools, edits files, runs commands, observes terminal output, iterates. Predates and helped define the multi-step agent UX in IDE.
- SWE-1.5 (released late 2025): Cognition's proprietary coding model purpose-built for Windsurf. Up to 950 tokens/sec — claimed 6x faster than Claude Haiku 4.5 and 13x faster than Sonnet 4.5 on equivalent agentic tasks. Speed comes from co-design with Fast Context + Codemaps rather than raw model superiority.
- Codemaps (early 2026): AI-annotated structural maps of the codebase, used both for human onboarding and as retrieval substrate. Generation can use Fast (SWE-1.5) or Smart (Claude Sonnet 4.5) mode. Sole differentiator no competitor has matched as of May 2026.
- Embedded Devin: Cognition's autonomous engineer agent is now invocable from within Windsurf for long-running async tasks.
- Model routing: Auto mode chooses SWE-1.5 for speed-critical edits and Claude/GPT for high-difficulty reasoning.

## Pricing
After a structural overhaul on March 19, 2026 (retired credit system, moved to daily/weekly quotas), current tiers:
- Free: limited daily quota
- Pro: $20/month (raised from $15) — full Cascade, SWE-1.5, daily/weekly user quotas
- Max: $200/month — high-volume quota, priority access
- Teams: $40/user/month
- Enterprise: custom

## Traction
- At acquisition (Jul 2025): $82M ARR, 350+ enterprise customers, hundreds of thousands of daily active users, enterprise ARR doubling quarter-over-quarter
- Combined Cognition entity ARR: $492M as of the May 2026 round; enterprise Devin usage growing 50% MoM for six months
- Ranks #1 on LogRocket AI Dev Tool Power Rankings (Feb 2026), ahead of Cursor and Copilot
- Cognition reportedly has 90% of its own code written by Devin (per CEO commentary on the May 2026 raise)

## Strategic Position
- Position: the credible #2 in AI-native IDEs and the only one to ship a proprietary agentic model + retrieval system co-design at parity-or-better than Cursor on a major axis (speed). Codemaps is the rare honest differentiator.
- Moat: ownership of Devin (the autonomous-engineer brand and tech), SWE-1.5 (vertically integrated model), and the Windsurf enterprise GTM motion inherited intact. Cognition founders Scott Wu / Steven Hao / Walden Yan are gold-medalist IOI competitors with a strong research team.
- Strategic risk: half the original IP and the CEO went to Google DeepMind — the Gemini agentic coding work now competes with Windsurf indirectly. The non-exclusive license means Google can use Windsurf tech freely.
- Saga-as-story: the M&A drama itself became marketing — by mid-2026 "the Windsurf comeback" is a recurring frame in coverage, and Cognition leaned into it with the SWE-1.5 + Codemaps launches.

## See Also
- [[Cursor]] — direct head-to-head competitor
- [[Cognition AI]] — parent company; see also Devin
- [[Zed]]
- [[Replit]]
- [[Trae]]
- [[AI-Native IDEs]]
- [[Agent Harness]]
- [[Codebase Indexing]]
- [[Market Landscape]]
