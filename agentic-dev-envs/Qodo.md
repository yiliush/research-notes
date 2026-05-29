---
tags: [tool, ide-extension, vscode, jetbrains, agent, code-review, code-quality]
created: 2026-05-28
---

# Qodo

Qodo (rebranded from CodiumAI in 2024) is the cluster's "quality-first" player — its differentiator is that the agentic workflow is anchored on test generation and pull-request review rather than greenfield code authoring. The product is split across three surfaces: Qodo Gen (IDE), Qodo Merge (PR review on GitHub/GitLab/Bitbucket/Azure DevOps), and Qodo Command (CLI for agentic CI workflows, launched June 2025). It's also the only player here that maintains a meaningful open-source artifact (the `pr-agent` repository) alongside a commercial offering.

## Origin
- Maker: Qodo (formerly CodiumAI), founded 2022, headquartered in Tel Aviv
- Rebranded from CodiumAI to Qodo in 2024 to disambiguate from Codeium/Windsurf
- License: Proprietary platform; `pr-agent` (Qodo Merge OSS) is open source
- Funding: Series A and earlier rounds disclosed; PitchBook tracks total raise in the tens of millions

## Adoption
- 682K VS Code Marketplace installs (extension ID `Codium.codium`)
- 492K JetBrains Marketplace installs
- 1M+ total developers (TechCrunch, company)
- Early Fortune 100 enterprise adopters

## Architecture
- Model support: Claude (Anthropic), GPT, Gemini, Grok 4, plus model routing; premium models cost more credits
- BYOK: Enterprise tier supports own model endpoints
- Agent harness: Qodo Gen (IDE chat, code, tests, local review), Qodo Merge (PR review agent), Qodo Command (CLI Lego-style agents for CI)
- MCP support: Yes — MCP integration in Qodo Command and IDE
- Codebase indexing: per-repo context; quality-focused retrieval optimized for test generation and review

## Pricing
- Developer (free): 30 PR reviews/month, 250 IDE/CLI credits/month
- Teams: $30/user/mo annual ($38/mo monthly)
- Enterprise: custom
- Credit-based system: standard LLM requests = 1 credit; Claude Opus = 5 credits; Grok 4 = 4 credits

## Differentiators
- Quality-first positioning: test generation and PR review are the headline features, not autocomplete
- Three coordinated surfaces (IDE + PR + CLI) sharing the same agent semantics
- Open-source `pr-agent` is widely deployed independently of the commercial product
- Strongest credit-transparency among proprietary tools in this cluster
- Targets the "AI code review" wedge that GitHub Copilot, Cursor, and Augment are all racing toward

## See Also
- [[VSCode Ecosystem]]
- [[GitHub Copilot]]
- [[Continue]]
- [[Cody]]
