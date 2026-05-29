---
tags: [tool, ide-extension, vscode, jetbrains, enterprise, sourcegraph]
created: 2026-05-28
---

# Cody (Sourcegraph) and Amp

Sourcegraph's Cody pivoted hard in 2025: free and Pro tiers were shut down on July 23, 2025, and the company split its product line into Cody (pure enterprise code intelligence at $59/user/mo) and Amp (a frontier agentic coding tool for individual developers and teams). The bet is that Sourcegraph's code graph — indexing across the entire enterprise monorepo — is the durable advantage, and that retail BYOK agents commoditize. Cody is the highest-priced individual offering of any extension in this cluster; Amp competes head-on with Cursor's Composer.

## Origin
- Maker: Sourcegraph, founded 2013
- Cody launched 2023 as a code search-grounded AI assistant for VS Code and JetBrains
- Amp launched 2025 as the agentic spinoff; rebrand from "Sourcegraph Cody" in some surfaces
- License: Proprietary (Cody desktop clients had source-available components historically)

## Adoption
- Cody no longer publishes consumer install counts after the free/Pro shutdown
- VS Code Marketplace listing remains live for enterprise users
- Sourcegraph itself indexes code at firms including Uber, Lyft, Plaid, GE, and most large banks
- Amp: free-forever tier reopened the consumer top of funnel post-Cody shutdown

## Architecture
- Model support: Anthropic Claude (Sonnet, Opus 4.x), OpenAI, Google Gemini, plus enterprise-hosted models
- BYOK: Enterprise can bring approved providers; not a consumer feature
- Agent harness: Amp Smart Mode for multi-step agent tasks; Cody enterprise focuses on chat, edit, and context retrieval
- MCP support: Yes — Amp ships an MCP client and integrates with Claude Code, Cursor, Codex
- Codebase indexing: Sourcegraph's code graph — cross-repo semantic search, symbol resolution across entire enterprise monorepos. This is the moat.
- Surfaces: VS Code, JetBrains, CLI (Amp), GitHub PR review

## Pricing
- Cody Free / Pro: discontinued July 23, 2025
- Cody Enterprise: from $59/user/mo
- Sourcegraph Enterprise (Cody + code search): starts at ~$16K/year with AI-feature credits
- Amp: Free-forever individual tier; custom for teams/enterprise

## Differentiators
- Cross-repository context: the only player whose context engine spans an entire enterprise's code graph, not just one repo
- Enterprise procurement maturity: SOC 2, on-prem, air-gapped, self-hosted deployments
- Decoupled product lines: enterprise code intelligence (Cody) vs. agentic individual tool (Amp)
- Premium pricing reflects positioning — not competing on $10–20 retail
- Agentic code review (Amp) extends the agent beyond authoring

## See Also
- [[VSCode Ecosystem]]
- [[GitHub Copilot]]
- [[Augment Code]]
- [[Tabnine]]
