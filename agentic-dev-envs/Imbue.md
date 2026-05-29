---
tags: [company, model-lab, reasoning-research, stealth-ish]
created: 2026-05-28
---

# Imbue

Imbue (formerly Generally Intelligent) is the quietest of the well-funded coding-model labs — a reasoning-and-code research outfit founded by Kanjun Qiu and Josh Albrecht that raised $200M in 2023 and has produced almost no public product output through May 2026, yet retains a serious technical reputation among ML researchers. Their thesis is that the bottleneck in coding agents is not scale but the data and training regime needed for "robust reasoning."

## Company / Origin
- Founded 2017 as Generally Intelligent by Kanjun Qiu (CEO) and Josh Albrecht (CTO). Rebranded to Imbue in late 2023.
- HQ: San Francisco.
- Headcount: ~60 as of early 2026 (Tracxn).
- Both founders are publicly active in the ML and rationalist communities; Qiu was formerly president of Sourcegraph.

## Funding & Valuation
- Series A 2022: $20M, Astera Institute and others
- Series B September 2023: $200M at >$1B valuation (Astera Institute, NVIDIA, Cruise CEO Kyle Vogt, Notion co-founder Simon Last, others) — TechCrunch, Sep 7 2023
- Total funding through May 2026: ~$232M
- No publicly reported funding rounds in 2024, 2025, or 2026. Notable as a sign of either capital efficiency or strategic disinterest in dilution while waiting for a model release.

## Product / Models
- No publicly released production coding model as of May 2026.
- Public technical output: a 2024 blog post on training infrastructure ("From bare metal to a 70B model: infrastructure setup and scripts"); open-source releases of evaluation harnesses; the CARBS hyperparameter sweeping tool.
- Stated research focus: foundation models optimized for reasoning, with an emphasis on coding as the canonical test environment.
- Compute base: ~10,000 H100 cluster (publicly disclosed in 2023).
- No SWE-bench Verified numbers; no public model card.

## Distribution
- None public as of May 2026. Imbue is the closest to a true research-lab posture in this cluster — closer to early Anthropic or pre-product DeepMind than to a commercial coding-model vendor.

## Strategic Position
- The quietest entry in the [[Coding Model Labs]] cluster. The lack of public model releases through 2024–2026 is interpretable as either (a) genuine research depth that will eventually produce a meaningful release, or (b) a stalled effort that's burning down its 2023 raise. The market currently treats it as the former, partly on the strength of Qiu and Albrecht's reputations.
- Strategic risk: the 2023 $200M raise was made in a fundraising environment where $1B "research lab" valuations were defensible without revenue. By May 2026, the bar for the next round is dramatically higher — peer labs ([[Reflection AI]] at $25B, [[Poolside]] at $12B) have either shipped or fundraised on aggressive timelines. Imbue's next round will need either a public model or a much-changed narrative.
- The "reasoning-first" framing is now table stakes — every frontier lab claims it. Imbue's original differentiation has been partly absorbed by Anthropic (Sonnet 4.x reasoning), OpenAI (GPT-5 reasoning), and DeepSeek (R1, R2).
- Possible scenarios: a late 2026 model release that validates the thesis; quiet acqui-hire by Nvidia (an existing investor) or a hyperscaler; or a graceful pivot to applied agent products.

## See Also
- [[Coding Model Labs]]
- [[Reflection AI]] — peer "reasoning research" framing
- [[Magic.dev]] — peer in slow-shipping high-funded category
- [[Poolside]] — peer
- [[Autonomous Coding Agents]]
- [[Sourcegraph]] — Qiu's prior employer
