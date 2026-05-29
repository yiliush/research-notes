---
tags: [tool, ide-extension, jetbrains, agent, incumbent]
created: 2026-05-28
---

# JetBrains AI Assistant and Junie

JetBrains' answer to the autonomous coding wave is split in two: AI Assistant (the chat/completion layer launched in 2023) and Junie (the agent, launched in early-access 2025 and GA January 2026). Junie is JetBrains' direct response to Cursor's Composer and GitHub Copilot's agent mode — fully autonomous multi-step coding inside IntelliJ, PyCharm, WebStorm, GoLand, RustRover, and the rest of the JetBrains lineup. In September 2026, JetBrains integrated Anthropic's official Agent SDK, making Junie a Claude-powered agent on the JetBrains platform. This is the only ADE in this cluster that lives natively in JetBrains rather than VS Code, which matters because JetBrains' ~17M registered users are mostly invisible to the VS Code-centric narrative.

## Origin
- Maker: JetBrains s.r.o., headquartered in Prague
- AI Assistant launched late 2023; Junie launched early access 2025, GA January 2026
- Claude Agent SDK integration: September 2026
- License: Proprietary

## Adoption
- JetBrains IDEs: ~17M registered users (company-reported, broad estimate)
- Junie ships inside all JetBrains IDEs with an active AI subscription
- Specific Junie active-user count not disclosed
- AI Assistant marketplace installs in the millions across JetBrains plugin repositories

## Architecture
- Model support: Anthropic Claude (Sonnet, Opus), OpenAI, Google Gemini, plus JetBrains' Mellum (their own code-completion model)
- BYOK: Limited to Enterprise tier
- Agent harness: Junie — autonomous planning, multi-file editing, terminal execution, test-iteration. Claude Agent SDK integration powers the deeper autonomous workflows.
- MCP support: Yes — MCP client added in 2025
- Codebase indexing: leverages JetBrains' existing program structure interface (PSI) — the deepest static-analysis-aware code understanding of any IDE
- Surfaces: IntelliJ IDEA, PyCharm, WebStorm, GoLand, RustRover, RubyMine, PhpStorm, CLion, Rider, DataGrip, Android Studio (via plugin)

## Pricing
- AI Free: $0 (limited credits)
- AI Pro: $10/mo individual ($100/year); ~$8/mo on annual billing
- AI Ultimate: $30/mo individual ($300/year)
- AI Enterprise: custom ($720/user/year for max credits per published rate cards)
- Business tiers (Pro $20/mo, Ultimate $60/mo) for team licensing
- Credit-based metering on premium models

## Differentiators
- PSI-grounded context: refactoring-aware, type-aware code understanding that VS Code extensions cannot replicate without their own language servers
- Deep IDE integration: Junie can invoke any IDE action (refactor, inspection, debugger) the user can
- Cross-language IDE breadth: a single agent surface across 10+ JetBrains IDEs
- Claude Agent SDK integration: JetBrains is the first major IDE to ship an SDK-level Anthropic integration
- The non-VS-Code anchor of the agentic IDE market

## See Also
- [[VSCode Ecosystem]]
- [[GitHub Copilot]]
- [[Continue]]
- [[Kilo Code]]
- [[Qodo]]
