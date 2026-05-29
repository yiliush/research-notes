---
tags: [model-provider, chinese, open-weight, code-model, alibaba]
created: 2026-05-28
---

# Qwen Coder

Qwen Coder is Alibaba's code-specialist model line — and as of May 2026, alongside DeepSeek V4, one of the two open-weight models that genuinely competes with Claude Sonnet on agentic coding benchmarks. Qwen3-Coder is the substrate beneath a surprising fraction of the global open-source coding-agent ecosystem, including Cerebras Code, Cline, Roo Code, Aider, and Alibaba's own Qwen Code terminal agent.

## Company / Origin
- Qwen (通义千问) is Alibaba Cloud's foundation-model line, launched 2023. Qwen Coder is the code-specialist branch.
- HQ: Hangzhou, China (Alibaba). Qwen team operates inside Alibaba DAMO Academy / Alibaba Cloud.
- Significant differentiator from peers: Qwen is the model line of a $250B+ market cap parent company with vast compute access, distinct from independent labs like DeepSeek or Mistral.

## Funding & Valuation
- Not separately funded — Qwen is an Alibaba internal program. Alibaba publicly committed >$50B in 2025 to AI infrastructure over the following three years, with Qwen as the primary beneficiary.
- This is Qwen's structural advantage: no fundraising bottleneck, no dilution constraints, and the compute / data flywheel of the Alibaba Cloud customer base.

## Product / Models
- **Qwen 2.5 Coder** (2024) — sizes 0.5B through 32B. The 32B Instruct variant scored 73.7 on the Aider benchmark, comparable to GPT-4o. Heavy adoption in OSS coding agents at the 32B size as the default "free local-deploy frontier" option through 2024–2025.
- **Qwen3-Coder 480B-A35B** (July 2025) — flagship: 480B total parameters, 35B active (MoE). Trained on 7.5T tokens with 70% code focus. State-of-the-art among open models on SWE-Bench Verified at release, matching Claude Sonnet 4 on agentic coding benchmarks.
- Post-training innovation: Alibaba introduced long-horizon RL ("Agent RL"), running 20,000 independent environments in parallel on Alibaba Cloud — a scale of RL training environment difficult for non-hyperscalers to match.
- **Qwen3-Coder-Next** (February 2026) — successor release, open-weight, designed for coding agents and local development. 44.3% on SWE-Bench Pro.
- All major Qwen Coder releases are open-weight (Apache 2.0 or Tongyi Qianwen License, both permissive for commercial use).

## Distribution
- Open weights on Hugging Face and ModelScope
- Alibaba Cloud Model Studio first-party API at competitive pricing
- Hosted by every major inference provider — most relevantly Cerebras, where Qwen3-Coder 480B runs at 2,000+ tokens/second (see [[Cerebras]])
- Available on OpenRouter, Together AI, Fireworks
- **Qwen Code** — Alibaba's own open-source terminal coding agent, modeled on Claude Code / Aider, optimized for Qwen3-Coder. Distributes the model alongside a reference agent harness.
- Natively integrated into [[Cline]], [[Roo Code]], [[Aider]], [[Continue]]; also a first-class option in [[Trae]] (ByteDance's IDE — Chinese coding-agent stack tends to prefer Qwen)

## Strategic Position
- The most under-recognized fact about the agentic coding market in 2026: a large fraction of US open-source coding agents are running Qwen Coder by default when users select "fast" or "cheap" modes, even when those users don't realize it.
- Alibaba's compute advantage (the 20,000-parallel-environment RL training claim) is the kind of capex moat that independent labs ([[DeepSeek]], [[Mistral]], [[Poolside]]) cannot match. If Qwen sustains the release cadence through 2026–2027, it likely becomes the default open-frontier code model.
- Geopolitically constrained in the same way as DeepSeek: US regulated enterprise procurement often excludes Chinese models, regardless of license. The on-prem / weights-download path is the workaround, but it requires customer technical sophistication.
- The Cerebras partnership is strategically important — Cerebras has effectively branded Qwen3-Coder as "the fast model" to a generation of Cline / OpenRouter users, building the brand into Western developer workflows in a way DeepSeek (which is more associated with the lab name) has not matched.

## See Also
- [[Coding Model Labs]]
- [[DeepSeek]] — peer
- [[Mistral Codestral]] — peer
- [[Cerebras]] — primary speed-inference partner
- [[Trae]] — ByteDance IDE that prefers Qwen
- [[Cline]] — major distribution surface
- [[Aider]]
- [[SWE-bench and Coding Benchmarks]]
