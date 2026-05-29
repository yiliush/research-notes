---
tags: [company, model-provider, european, code-model, open-weight]
created: 2026-05-28
---

# Mistral Codestral

Codestral is Mistral AI's code-specialist model line — the European frontier-lab's bet that a focused code model on permissive licensing terms can win the developer mindshare that the much larger US labs claim through API integrations. As of May 2026, Codestral 25.01 and Codestral Mamba are the most-deployed European-origin code models, and Mistral itself has become Europe's most valuable AI company at $13.7B.

## Company / Origin
- Mistral AI founded April 2023 by Arthur Mensch (CEO, ex-DeepMind), Guillaume Lample (Chief Scientist, ex-Meta), and Timothée Lacroix (CTO, ex-Meta).
- HQ: Paris, France.
- Headcount: ~200 as of early 2026.
- Mistral's strategic significance is partly geopolitical — it is the only non-US, non-Chinese lab in serious contention at the frontier, and the EU has explicitly framed it as European AI sovereignty.

## Funding & Valuation
- Series A June 2023: ~€105M, Lightspeed and others (largest seed in European tech history at the time)
- Series B December 2023: ~€385M at €2B valuation
- Series C September 2025: €1.7B at €11.7B post-money. ASML committed €1.3B as the largest shareholder (~11% stake), pushing valuation to $13.7B
- Debt financing March 2026: $830M for new data centers near Paris and Sweden
- Total raised through May 2026: ~$3.05B equity + $830M debt
- Reported 2025 ARR: >$400M, targeting >$1B by EOY 2026

## Product / Models
- **Codestral 22B** (May 2024) — original release. Code-specialist, 32K context, available under Mistral's non-production license (free for research and individual use; commercial use requires a license).
- **Codestral Mamba 7B** (July 2024) — first major code model built on the Mamba architecture (linear-time attention). 75.0% HumanEval — strongly competitive at 7B scale vs. CodeGemma 7B (61.0%), CodeLlama 34B (31.1%), DeepSeek v1.5 7B (65.9%).
- **Codestral 25.01** (January 2025) — flagship update. Under 100B parameters, 256K context window. 86.6% HumanEval. Marketed as "the clear leader for coding in its weight class," 2x faster than the prior version.
- Coverage: 80+ programming languages, with fill-in-the-middle, code correction, and test generation.
- No public SWE-bench Verified leadership claim — Codestral is positioned for low-latency completion and editor integration rather than autonomous agent workloads.

## Distribution
- API: la Plateforme (Mistral's first-party API), Google Vertex AI, Azure AI Foundry, Amazon Bedrock
- IDE plugins: official partnerships including Continue.dev, JetBrains, and others; ships natively inside the [[Continue]] coding agent
- Local deployment: weights downloadable for the open variants; commercial license required for production use
- le Chat (Mistral's consumer chat product) routes code questions to Codestral

## Strategic Position
- Mistral occupies the "European sovereign code model" position uncontested — no other EU lab is close. This is real procurement leverage with EU governments, regulated industries, and the European Investment Bank's procurement preferences.
- The licensing model (open-ish weights, commercial license required) is a middle path between fully-open ([[DeepSeek]], [[Qwen Coder]]) and fully-closed (Anthropic, OpenAI). It has been less commercially successful as a moat than either extreme — open-weight competitors have closed the capability gap, and closed-weight competitors have stronger product distribution.
- Codestral's HumanEval lead does not translate to SWE-bench Verified leadership, where the model lags Qwen3-Coder and DeepSeek V4 substantially. The "code completion is the use case" framing is increasingly the consolation prize as the market moves toward agentic workloads.
- ASML's investment is strategically interesting — it ties Mistral to the European semiconductor lithography monopoly and probably aligns Mistral's roadmap toward EU industrial customers rather than US developer-tooling distribution.

## See Also
- [[Coding Model Labs]]
- [[DeepSeek]] — open-weight competitor
- [[Qwen Coder]] — open-weight competitor
- [[Continue]] — major distribution partner
- [[Poolside]] — adjacent European-HQ enterprise code lab
- [[Enterprise Adoption]]
