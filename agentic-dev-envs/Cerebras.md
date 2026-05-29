---
tags: [company, inference-provider, hardware, wafer-scale, speed]
created: 2026-05-28
---

# Cerebras

Cerebras is the wafer-scale-chip company that became, almost incidentally, the fastest commercial inference provider for open-weight coding models. Their partnership with Cline in August 2025 — delivering Qwen3-Coder 480B at 2,000 tokens per second — reframed what "fast" means for a coding agent, and made Cerebras a strategic dependency for several major harnesses.

## Company / Origin
- Founded 2015 by Andrew Feldman (CEO), Gary Lauterbach, Michael James, Sean Lie, and Jean-Philippe Fricker — the team behind SeaMicro (acquired by AMD in 2012).
- HQ: Sunnyvale, California.
- Headcount: ~400 as of early 2026 (estimate from S-1 filing range).
- The thesis from day one: build single-wafer chips rather than splitting silicon into discrete GPUs.

## Funding & Valuation
- Total private funding pre-IPO: ~$720M across multiple rounds
- Series H February 2026: $1B led by Tiger Global, with AMD, Benchmark, Coatue, Fidelity participating
- Filed S-1 April 17 2026, targeting Nasdaq listing at ~$23B valuation
- IPO May 13–14 2026 (CBRS), price range $125–$135, valuing at $26–$27B
- 2025 revenue: $510M (+76% YoY)
- 86% revenue concentration in two UAE-based entities (G42 and Group 42 entities) per S-1 — a major risk factor
- $20B+ Master Relationship Agreement with OpenAI announced January 2026 for 750 MW of inference compute capacity

## Product / Models (Hardware & Inference)
- **WSE-3** (Wafer-Scale Engine, 3rd gen) — single chip 46,225 mm² (57x larger than Nvidia H100). 4 trillion transistors, 900,000 AI cores, 44 GB on-chip SRAM, 21 PB/s memory bandwidth. Manufactured on TSMC 5nm.
- All model weights live on-chip — no off-chip memory bottleneck during inference. This is the speed advantage.
- **Cerebras Inference Cloud** — hosted inference service. Supports Llama, Qwen, DeepSeek, and other major open-weight models.
- **Cerebras Code** — code-specific product launched August 2025. Bundles Qwen3-Coder 480B at 2,000 tok/s under a developer-facing subscription. Starting at $50/month.
- Pricing on the API side: $2/Mtok input or output for Qwen3-Coder 480B — about 100x faster than Gemini 2.5 Flash for generation of long code outputs (1,000 lines of JS in 4 seconds vs. 30 seconds Gemini vs. 80 seconds Sonnet 4).

## Distribution
- First-party: Cerebras Inference Cloud, Cerebras Code subscription
- Partner channels: OpenRouter (where many Cline / Aider / Roo Code users access them), Hugging Face Inference
- Direct integrations: **Cline x Cerebras** (announced August 2025) — the marquee coding-agent partnership, marketed as "instant code generation"
- OpenAI inference partnership: 750 MW capacity, signaling that OpenAI itself is consuming Cerebras inference for some workloads
- G42 / Middle East: still the largest revenue source, sovereign-AI inference deployments

## Strategic Position
- Cerebras occupies a category of one in commercial wafer-scale inference. The closest competitor is Groq with the LPU (different architecture, similar "speed at the cost of model size flexibility" tradeoff), and Groq is now effectively inside Nvidia (see [[Groq]]).
- Strategic vulnerability is customer concentration — 86% of revenue from UAE entities is the kind of number that makes public-market investors nervous and dependent on the OpenAI ramp closing on schedule.
- The coding-agent partnership strategy is shrewd: agents are inherently multi-turn and latency-sensitive, so speed advantages compound in user-perceived quality in a way that single-shot chat doesn't. The Cline partnership made "Cerebras Code" a household name in the OSS agent community within months.
- Open question: if the entire industry standardizes on Cerebras / Groq for inference, do model labs ([[DeepSeek]], [[Qwen Coder]]) capture the value or do the inference providers? Cerebras's bet is that the wafer-scale moat is durable enough that they keep meaningful gross margin even as model weights commoditize.

## See Also
- [[Coding Model Labs]]
- [[Groq]] — peer in speed-inference niche
- [[Inception Labs]] — alternative architectural approach to speed
- [[Qwen Coder]] — flagship hosted model
- [[DeepSeek]] — hosted model
- [[Cline]] — anchor coding-agent partner
- [[OpenHands]]
- [[Aider]]
