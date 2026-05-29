---
tags: [tool, ide-extension, vscode, jetbrains, enterprise, well-funded]
created: 2026-05-28
---

# Augment Code

Augment Code is the heaviest-funded VS Code-extension player in this cluster — $252M total, including a $227M Series B at a ~$977M valuation — and the one most explicitly built for the "large, complex codebase" problem. Founded 2022 by ex-Microsoft principal engineer Igor Ostrovsky and ex-Google AI researcher Guy Gur-Ari, it emerged from stealth in April 2024 and has since shipped IDE agents, a Mac desktop workspace ("Intent"), and a GitHub code-review agent. As of May 2026 it ranks #1 on SWE-bench Pro at 51.80% and claims 100K+ developers including Fortune 500s.

## Origin
- Maker: Augment Computing, Inc., founded 2022, emerged from stealth April 2024
- Founders: Igor Ostrovsky (ex-Microsoft, founding engineer at Pure Storage), Guy Gur-Ari (ex-Google AI)
- License: Proprietary
- Funding: $252M total; $227M Series B led by Sutter Hill Ventures (Index Ventures, Innovation Endeavors, Lightspeed, Meritech). ~$977M valuation

## Adoption
- 100K+ developers on platform (company-reported)
- Fortune 500 customers
- #1 on SWE-bench Pro: 51.80%
- VS Code Marketplace listing active; specific install count not prominently published
- JetBrains plugin available

## Architecture
- Model support: Claude (Anthropic), with model routing internally; proprietary fine-tunes
- BYOK: not a standard offering — Augment sells the full stack
- Agent harness: IDE agents with task lists, multi-step workflows, persistent memories; Intent (Mac desktop workspace); GitHub code review agent
- MCP support: Yes — enhanced MCP tool support added in 2025
- Codebase indexing: proprietary Context Engine — handles 400K+ files, builds a live semantic graph of code, dependencies, docs, issues, recent changes. This is the marquee differentiator.
- Surfaces: VS Code, JetBrains, terminal, Intent (Mac), GitHub PR review

## Pricing
- Indie: $20/mo (40K credits, 1 user)
- Standard: $60/dev/mo (130K credits)
- Max: $200/dev/mo (450K credits)
- Enterprise: custom (20+ users)
- "Intent" credit-based pricing reflects model usage rather than seat-only

## Differentiators
- Context Engine at 400K+ files: built for monorepos and legacy codebases that smaller context windows cannot reach
- Persistent memories across sessions and surfaces
- Multi-surface coverage: in-IDE + desktop workspace (Intent) + GitHub code review
- SWE-bench Pro #1 claim is the most credible benchmark result among proprietary VS Code-extension agents
- Capital depth: longest runway to play the enterprise sales cycle

## See Also
- [[VSCode Ecosystem]]
- [[Cody]]
- [[Tabnine]]
- [[GitHub Copilot]]
