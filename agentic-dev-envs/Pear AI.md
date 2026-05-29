---
tags: [tool, open-source, ai-ide, cursor-alternative, yc-backed, controversy, ade-cluster]
created: 2026-05-28
---

# Pear AI

Pear AI is a VS Code fork positioned as an open-source Cursor alternative. It became infamous in September 2024 when its YC funding announcement revealed the project was a near-verbatim rebranding of [[Continue]] — same codebase, "Continue" replaced everywhere with "PearAI" — released under a closed "Pear Enterprise License" that the founder admitted was written by ChatGPT. The resulting backlash forced a re-licensing under Apache 2.0 and dented YC's reputation. By May 2026 the project is still active but has not recovered momentum: 690 stars vs. competitor [[Void]] at ~28.8k.

## Origin
- Founded by Duke Pan and Nang Ang (~2024). YC S24 batch ($375k YC standard deal). Subsequently raised ~$1M seed from Goodwater Capital, Multimodal Ventures, Orange Fund, ExitFund and angels — total funding ~$1.25M as of May 2026.
- September 2024 controversy: TechCrunch and indie-developer Twitter accused Pear of plagiarism. Both Pear and Continue are YC companies, which intensified the criticism of YC's diligence.
- Founder Duke Pan posted an apology on Hacker News, switched license from "Pear Enterprise License" (ChatGPT-generated) to Apache 2.0, and committed to disclosing the Continue fork relationship publicly.

## Adoption
- GitHub stars verified May 2026: ~690 on `trypear/pearai-app`. Tiny by category standards.
- 128k+ total commits in the repo (inherited from VSCode upstream).
- 50+ contributors listed in acknowledgements.
- The AI functionality lives in `pearai-submodule`, a fork of Continue.

## Architecture
- VS Code fork (95.5% TypeScript).
- AI submodule = Continue fork = inherits Continue's provider integrations, indexing, autocomplete, and chat.
- Multi-provider model support (Anthropic, OpenAI, local via Ollama).
- License: Apache 2.0 (post-controversy).

## Pricing
- Free OSS. A "PearAI Pro" hosted tier exists with bundled inference credits, around $20/month — pricing has shifted multiple times.

## Differentiators
- The honest answer is "marketing." There is no technical differentiator vs. Continue. The pitch is: a more polished installer, an opinionated default configuration, and a brand.
- Post-controversy, Pear has shipped some original work — UI changes, an agent mode, a "search" command — but it's incremental on top of Continue.
- The PearAI story is now itself the artifact: it's the cautionary tale cited every time a VC-backed YC startup gets accused of rebranding OSS.

## Strategic Position
- Lost the OSS-Cursor-alternative race to [[Void]] (which started clean and accumulated 28k+ stars) and [[Aide]] (which had real technical innovation before being archived).
- Continue itself outperforms Pear on every metric — stars, enterprise traction, model integrations.
- Real question: does Pear pivot or fade? With $1.25M raised, runway is short, and the brand has a permanent asterisk.

## See Also
- [[Continue]] — the project Pear forked; now the dominant OSS Cursor alternative
- [[Void]] — direct competitor that played it straight
- [[Aide]] — the other OSS VS Code fork
- [[Cursor]] — the product being cloned
- [[Green Shoots]]
