---
tags: [company, inference-provider, hardware, lpu, speed, nvidia-deal]
created: 2026-05-28
---

# Groq

Groq is the LPU (Language Processing Unit) inference company that — until Nvidia's $20B licensing deal in December 2025 — was Cerebras's main competitor in the "fast inference for agents" niche. As of May 2026, Groq exists in an unusual state: its core IP is licensed to Nvidia, its founder and ~80% of its engineering team have moved inside Nvidia's Real-Time Inference division, and the standalone Groq business continues to operate while its technology becomes part of Nvidia's Vera Rubin platform.

## Company / Origin
- Founded 2016 by Jonathan Ross (CEO until the Nvidia deal) — the original architect of Google's TPU before leaving to build Groq.
- HQ: Mountain View, California.
- Pre-deal headcount: ~500.

## Funding & Valuation
- Series A through D 2017–2024: ~$1B+ across multiple rounds
- August 2024: $640M at $2.8B valuation, led by BlackRock, with Cisco, Samsung Catalyst, KDDI
- Late 2025 valuation: ~$7B before the Nvidia deal
- **December 24 2025: $20B non-exclusive technology licensing deal with Nvidia.** Jonathan Ross + ~80% of Groq engineering joined Nvidia. The deal is structured as a license, not an acquisition, but the practical effect is acqui-hire-like. (Tom's Hardware, IntuitionLabs, Techi, December 2025 reporting)
- Standalone Groq continues to operate post-deal with remaining team

## Product / Models (Hardware & Inference)
- **LPU (Language Processing Unit)** — custom inference architecture optimized for sequential token generation rather than batched training. SRAM-based, deterministic execution, very low latency.
- **GroqCloud** — first-party inference cloud. Hosts Llama models (Groq is Meta's official fast-inference partner for the Llama API as of April 2025), DeepSeek, Qwen, Mixtral.
- **Groq 3 LPU** (announced GTC 2026) — first product from the Nvidia partnership. Manufactured by Samsung on 4nm. Slots into Nvidia's Vera Rubin platform as a dedicated decode-phase co-processor alongside GPUs. Target throughput for agentic communications: up to 1,500 tokens/second.
- Groq 3 shipping in Q3 2026. AWS announced GTC 2026 they will deploy Groq 3 alongside more than one million Nvidia GPUs.

## Distribution
- First-party: GroqCloud API
- OpenRouter, Hugging Face Inference, Together AI fallback routing
- Meta Llama official API partnership (April 2025)
- US Department of Energy partnership for AI infrastructure (post-deal)
- Direct coding-agent integrations: Aider, Cline, Continue, Roo Code all support Groq as a provider option

## Strategic Position
- Pre-Nvidia-deal Groq was the natural Cerebras competitor — different architecture (LPU vs. wafer-scale), similar promise (1,000+ tok/s inference for sequence generation).
- Post-deal Groq is in a strategically ambiguous position: the standalone company still exists and still serves customers, but the most differentiated future product (Groq 3) is a Nvidia roadmap item. The founder is at Nvidia. The talent is at Nvidia.
- For coding agents, the practical implication is that "Groq" the API endpoint may eventually become Nvidia's inference offering by another name. The Llama API partnership and the DOE deal suggest Groq continues to operate, but Nvidia is the strategic owner.
- The deal itself is informative about the inference market structure as of 2026: Nvidia paid 2.9x Groq's prior valuation as effectively a defensive move against the wafer-scale + LPU architectures eating its inference market. This is the strongest possible signal that fast-inference-for-agents is a strategic priority at the chip-vendor level.
- Vs. [[Cerebras]]: Cerebras stayed independent and IPO'd. Both companies validated the "GPUs are not the right shape for token-by-token sequence generation" thesis. Cerebras owns the wafer-scale win; Nvidia/Groq now owns the SRAM-deterministic-LPU win.

## See Also
- [[Coding Model Labs]]
- [[Cerebras]] — primary peer
- [[Inception Labs]] — alternative speed bet via architecture
- [[Qwen Coder]] — hosted model
- [[DeepSeek]] — hosted model
- [[Cline]]
- [[Aider]]
- [[Continue]]
