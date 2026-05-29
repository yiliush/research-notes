---
tags: [company, model-lab, agent-vendor, vertical-integration]
created: 2026-05-28
---

# Cognition Labs

Cognition Labs is the company behind Devin and (post-acquisition) Windsurf, and one of the few entities in the ADE market that owns both an agent harness and a frontier-grade in-house coding model. SWE-1.5 (their proprietary model, released October 2025) is the strongest publicly-disclosed proof that a vertically-integrated harness + model team can beat pure model labs on real IDE workloads.

This note focuses on Cognition as a model-training organization. For the agent product, see [[Devin]]; for the IDE, see [[Windsurf]].

## Company / Origin
- Founded 2023 by Scott Wu (CEO), Steven Hao (CTO), and Walden Yan. The founding team was unusual for the cohort: all International Olympiad in Informatics medalists, with prior careers at Scale AI, Lunchclub, and various research labs.
- HQ: San Francisco.
- Headcount: ~150 by early 2026, growing rapidly after the Windsurf integration.

## Funding & Valuation
- Seed 2023: ~$21M, Founders Fund and others
- Series A March 2024: $176M at $2B valuation, led by Founders Fund (with Khosla, Conviction Partners participating)
- Series B 2024–2025 round at ~$4B
- Late 2025: ~$10.2B valuation per reporting
- Windsurf acquisition: ~$250M in cash and stock, December 2025 — Cognition picked up the Windsurf team after the OpenAI acquisition fell apart following Google's $2.4B Codeium licensing deal
- Total raised through May 2026: well over $1B in primary capital

## Product / Models
- **SWE-1** — first proprietary coding model, an internal release used inside Devin's agentic loop through 2024 and early 2025.
- **SWE-1.5** (released October 30 2025) — frontier-size proprietary coding model. Hundreds of billions of parameters. Achieves 40.08% on SWE-Bench Pro — "near-frontier performance" — at 950 tokens/second, claimed 6x faster than Claude Haiku 4.5 and ~13x faster than Sonnet 4.5.
- Training history: the SWE model family was started by the Windsurf / Codeium team in May 2025 (before the OpenAI acquisition collapsed); Cognition acquired and accelerated the work post-Windsurf integration.
- **Codemaps** (2026) — a code-comprehension layer built on top of SWE-1.5, shipped inside Windsurf.
- Distribution of SWE-1.5: primarily inside Windsurf Cascade and inside Devin. Not currently available as a standalone public API for arbitrary third-party agents.

## Distribution
- SWE-1.5 ships embedded inside Cognition's own products: [[Devin]] (autonomous agent), [[Windsurf]] (IDE), and Devin-Windsurf integration (the "embedded Devin" capability).
- No general-availability API for SWE-1.5 as of May 2026 — the model is treated as a product moat, not a sold component.

## Strategic Position
- The case study for the "harness AND model is the moat" hybrid bet. Cognition built the agent first (Devin), found they were paying margin to Anthropic and OpenAI on every Devin turn, and decided to train their own. The acquisition of Windsurf bought them both the training know-how (Codeium had been training models since 2022) and the IDE distribution surface.
- SWE-1.5's positioning is unusual: not the smartest model in the market, but explicitly optimized for the agent loop — fast enough to run many turns per task, cheap enough to run many tasks in parallel, smart enough to clear the SWE-Bench Pro bar.
- Threats: (1) Cursor's Composer-2 occupies the same "fast model trained for IDE workloads" niche with a much larger user base. (2) Anthropic's pricing and rate-limit pressure on the harness layer makes the "save margin by training your own" pitch progressively weaker as Claude pricing falls. (3) Open-weight models ([[Qwen Coder]], [[DeepSeek]]) are closing the gap fast enough that the cost of maintaining a proprietary model line is hard to justify long-term unless Cognition keeps shipping meaningful capability improvements at SWE-1.5's velocity.

## See Also
- [[Coding Model Labs]]
- [[Devin]] — the agent product
- [[Windsurf]] — the IDE
- [[Cursor]] — direct competitor on both axes
- [[The Windsurf Saga]] — context on the December 2025 acquisition
- [[Autonomous Coding Agents]]
