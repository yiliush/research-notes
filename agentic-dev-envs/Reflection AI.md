---
tags: [company, model-lab, autonomous-agent, frontier-code-model]
created: 2026-05-28
---

# Reflection AI

Reflection AI is the most aggressively-funded "autonomous coding agent + own frontier model" bet, raising from $545M to $25B valuation in 12 months on the credibility of its founders' DeepMind pedigree. As of May 2026 the company has shipped Asimov (a code-comprehension agent) but no public frontier model — making it the cohort's purest narrative valuation.

## Company / Origin
- Founded 2024 by Misha Laskin (CEO, ex-DeepMind research scientist, Gemini training contributor) and Ioannis Antonoglou (CTO, ex-DeepMind, a key architect of AlphaGo).
- HQ: New York / San Francisco (split).
- Headcount: ~50 as of early 2026 (per Sacra, Dealroom).

## Funding & Valuation
- Seed / early round 2024
- March 2025: $130M at $545M valuation
- October 2025: $2B Series B at $8B valuation, led with Nvidia participation — a ~15x markup in seven months (SiliconANGLE, Pulse2, Oct 2025)
- March 2026: in talks to raise $2.5B at $25B valuation (Sacra, Turing Post)
- Total committed funding through May 2026: ~$4.6B if the March round closes as reported
- Investor framing: positioned as "an open-model alternative to OpenAI" — Reflection has publicly committed to releasing frontier-class open weights, partly as a national-security pitch to US-aligned customers concerned about [[DeepSeek]]

## Product / Models
- **Asimov** (debut July 2025) — code-research / code-comprehension agent. Continuously indexes GitHub repositories, architecture docs, and dev tools. Designed for the ~70% of engineering time spent reading and understanding existing systems rather than writing new code. Targets engineering teams at large companies.
- Asimov uses Reflection's own models routed alongside external frontier models — they have not disclosed which.
- **Frontier model** — promised, not yet public as of May 2026. The October 2025 raise was explicitly framed around training a frontier open model with safety research. The March 2026 raise reportedly accelerates that timeline.
- No public SWE-bench Verified scores from Reflection's own model.

## Distribution
- Asimov is sold to engineering organizations directly; access is gated by waitlist as of May 2026.
- Future model distribution intended to be open-weight, per Laskin's public statements through 2025–2026.
- No public API or general-availability product yet.

## Strategic Position
- The DeepMind pedigree is doing enormous valuation work. Laskin + Antonoglou are credible enough that investors are pricing the team like a $25B asset before any model has shipped.
- Strategic positioning: deliberately occupies the gap between Anthropic / OpenAI (closed weights, US) and [[DeepSeek]] / [[Qwen Coder]] (open weights, China). Frames itself as "the open frontier model from a US lab" — a national-security and procurement pitch.
- The Asimov bet (code comprehension first, code generation second) is contrarian — most coding agents prioritize writing code. If "reading and understanding the codebase" is the actual bottleneck for enterprise adoption, this could be a wedge.
- Highest-risk valuation in the cohort: $25B without a released frontier model is a bet that the team executes Gemini-class training in-house faster than [[Poolside]] or [[Magic.dev]] catch up — and faster than the next [[DeepSeek]] release commoditizes the open-frontier position entirely.
- The 2025 round had Nvidia as an investor; the March 2026 round positioning suggests Nvidia is doubling down on multiple "national open frontier" bets in parallel.

## See Also
- [[Coding Model Labs]]
- [[Poolside]] — direct peer
- [[Magic.dev]] — direct peer
- [[DeepSeek]] — the open-frontier competitor they explicitly position against
- [[Imbue]] — adjacent in "reasoning + coding" research framing
- [[Autonomous Coding Agents]]
- [[Devin]]
