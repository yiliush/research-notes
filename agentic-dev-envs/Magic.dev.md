---
tags: [company, model-lab, long-context, frontier-code-model]
created: 2026-05-28
---

# Magic.dev

Magic.dev is the long-context maximalist of the coding-model cohort: their bet is that if you can fit 100 million tokens of code into a model's working memory, retrieval, vector search, codebase indexing, and most of the IDE plumbing become obsolete. They have raised over $1B from Eric Schmidt, CapitalG, Atlassian, Nat Friedman, Daniel Gross, and Sequoia, partnered with Google Cloud on a custom supercomputer, and as of May 2026 have shipped technical milestones but no public frontier product.

## Company / Origin
- Founded 2022 by Eric Steinberger (CEO) and Sebastian De Ro (CTO). Both come from ML research backgrounds; Steinberger previously founded ClimateScience.
- HQ: San Francisco.
- Headcount: ~50 as of early 2026 — famously small for the capital raised.

## Funding & Valuation
- Series A 2023: ~$117M (Nat Friedman, Daniel Gross, CapitalG)
- Funding Aug 2024: $320M led by CapitalG, with Atlassian, Sequoia, Nat Friedman, Daniel Gross, Eric Schmidt's funds (TechCrunch, Aug 29 2024)
- Reported July 2025: in talks to raise an additional $200M at ~$1.5B valuation (tripling from a few months prior, per Developer-Tech and ODSC reporting)
- Total raised through May 2026: ~$1.02B
- Strategic partnership: Magic-G4 supercomputer (H100s) with Google Cloud, Magic-G5 (Grace Blackwell) scaling to "tens of thousands of GPUs"

## Product / Models
- **LTM-2-mini** (released Aug 2024) — first model with a 100 million token context window, equivalent to ~10 million lines of code or ~750 novels.
- The technical claim: their sequence-dimension algorithm is ~1000x cheaper than the attention mechanism in Llama 3.1 405B at 100M-token context. Llama 3.1 405B would need 638 H100s per user for the KV cache alone; LTM-2-mini uses a small fraction of a single H100's HBM.
- **HashHop** evaluation — Magic's own benchmark of long-context reasoning, designed to defeat the "needle in a haystack" criticism by requiring multi-hop reasoning across the entire context.
- **CTM-1 / LTM** is the broader family name; no full-scale general-availability product has shipped by May 2026.
- No public SWE-bench Verified numbers as of May 2026 — a notable absence for a frontier-coding lab.

## Distribution
- No public API as of May 2026. No IDE plugin. No enterprise self-serve.
- Strategy appears to be selective enterprise pilots while the model line matures.
- Google Cloud is the inference partner — Magic-G4/G5 supercomputers are the dedicated compute.

## Strategic Position
- The 100M-token context bet is genuinely interesting: if it works at frontier quality, it eats the entire [[Codebase Indexing]] cluster — no more embeddings, no more retrieval, no more chunking, no more incremental re-index on every save. Just put the whole monorepo in context.
- The problem: long context has gotten dramatically cheaper across the industry. Gemini 2.5 supports 1M+ tokens. Claude Sonnet supports 1M. The differentiation gap has narrowed from "10x" to "100x," but the use case for 100M tokens specifically over 1M tokens for routine coding has been hard to demonstrate.
- Highest risk in the cohort of "model is the moat" bets: shipping cadence has been slow, no SWE-bench leadership, no enterprise design wins publicly disclosed, and the funding round in July 2025 priced flat-to-down vs. peer labs ([[Reflection AI]] at $25B, [[Poolside]] at $12B).
- The Google Cloud partnership is meaningful — it gives them compute access without raising commensurate dilution — but also ties their future to Google's strategy in coding agents ([[Jules]], [[Gemini CLI]]).

## See Also
- [[Coding Model Labs]]
- [[Poolside]] — peer frontier-code lab
- [[Reflection AI]] — peer
- [[Codebase Indexing]] — what long context would obsolete
- [[Cursor]] — current incumbent of the retrieval-heavy approach
- [[Gemini CLI]] — Google's own coding agent
