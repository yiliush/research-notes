---
tags: [company, model-provider, chinese, open-weight, frontier-code-model]
created: 2026-05-28
---

# DeepSeek

DeepSeek is the Chinese frontier lab that has done more than any other entity to collapse the commercial moat around closed-weight coding models. Its V3, R1, and V4 model lines — released under permissive open licenses — have repeatedly matched or beaten US closed-weight frontier models on code benchmarks at a fraction of the inference cost, forcing every Western lab to either match the open release or justify their pricing premium on something other than raw capability.

## Company / Origin
- Founded July 2023 by Liang Wenfeng, who is also co-founder of High-Flyer (a Chinese quantitative hedge fund). DeepSeek is owned and funded by High-Flyer.
- HQ: Hangzhou, China.
- Headcount: small relative to peers — reported figures range from 150 to 300 through 2025, growing in 2026.
- Liang is a hedge-fund billionaire who has publicly committed to AGI as the company's primary goal, with open-source as a deliberate strategic choice.

## Funding & Valuation
- Originally funded entirely from High-Flyer's quantitative trading profits — no external venture capital through 2024.
- Early 2026: completed a round from Chinese-government-backed investors at a $50B valuation.
- May 2026: in the middle of a 70B yuan (~$10B) funding round, with Liang reportedly committing up to 20B yuan (~$2.94B) personally (Bloomberg, The Information, Dataconomy — May 2026).
- The financing strategy is unusual: the round is being raised even as Liang publicly says DeepSeek will prioritize research over commercialization.
- US export controls on advanced semiconductors are the central constraint — DeepSeek has substituted Huawei Ascend chips for some workloads.

## Product / Models
- **DeepSeek Coder V1 / V2** (2024) — code-specialist models, V2 hit 61 SWE-bench Pro / 51 SWE-bench Verified as open-weight reference points.
- **DeepSeek V3** (December 2024) — 671B MoE (37B active). Matches or beats GPT-4o and Claude 3.5 Sonnet on most code benchmarks. The release that triggered Silicon Valley's January 2025 "DeepSeek shock."
- **DeepSeek V3-0324 / V3.1 / V3.2** (2025–2026) — incremental improvements, with V3.2 tested for SWE-bench in early 2026.
- **DeepSeek R1** (January 2025) — reasoning model, first major open frontier reasoning release. Sparked global reproduction efforts.
- **DeepSeek R1-0528** (May 2025) — significant R1 upgrade.
- **DeepSeek V4** (April 2026) — 1T parameters, trained on 32T+ tokens, native 1M-token context. ~81% SWE-bench Verified per NxCode reporting. Released under MIT License. Inference cost reported as $0.30 per million tokens.
- All major releases are under permissive open licenses (MIT for the most recent).

## Distribution
- Open weights on Hugging Face under MIT License
- DeepSeek's own first-party API at extremely aggressive pricing (often 10–50x cheaper per token than Anthropic / OpenAI equivalents)
- Hosted on every major inference provider: Together AI, Fireworks, Groq, Cerebras (Qwen3 specifically, see [[Cerebras]] note), OpenRouter
- Major Western coding agents — [[Aider]], [[Continue]], [[Cline]], [[Roo Code]] — all natively support DeepSeek model selection

## Strategic Position
- The single largest source of pricing pressure on US coding-model vendors. Every Cursor / Claude Code customer can do the math on "Claude Sonnet at $3-15/Mtok vs. DeepSeek V4 at $0.30/Mtok" and demand justification for the price gap.
- The geopolitical dimension is unavoidable: US enterprises in regulated sectors (defense, healthcare, finance) often cannot legally deploy DeepSeek-hosted services, which is why [[Poolside]] and [[Reflection AI]] explicitly position as "Western sovereign alternatives." This creates a bifurcated market.
- Liang's commitment to open weights even as the lab raises commercial capital is a deliberate strategic anchor — the open-weight position itself is the moat. If DeepSeek went closed-weight, it would lose the distribution network across global agents that makes its models the de-facto open frontier.
- Largest threat to DeepSeek's position is not a US lab but its own peer [[Qwen Coder]] — which has caught up on code-specific capability and is backed by Alibaba's much larger compute budget.

## See Also
- [[Coding Model Labs]]
- [[Qwen Coder]] — Chinese peer
- [[Mistral Codestral]] — European peer
- [[Reflection AI]] — positions explicitly against DeepSeek
- [[Cerebras]] — primary speed-inference partner
- [[Aider]] — major distribution surface
- [[Cline]]
- [[SWE-bench and Coding Benchmarks]]
