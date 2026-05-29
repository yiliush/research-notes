---
tags: [tool, ide-extension, vscode, microsoft, agent, incumbent]
created: 2026-05-28
---

# GitHub Copilot

The 800-pound gorilla of AI coding assistance. GitHub Copilot is Microsoft's flagship coding agent embedded in VS Code, Visual Studio, JetBrains, Xcode, and the github.com web surface. By May 2026 it sits at roughly 26M total users and 4.7M paid subscribers — a scale no competitor approaches — and its agent mode plus the Copilot coding agent (the productized successor to Copilot Workspace) have transformed it from autocomplete into a credible autonomous coding harness.

## Origin
- Maker: GitHub (Microsoft), launched June 2021 as autocomplete; GA October 2021
- Agent mode launched in preview Feb 2025; GA on VS Code and JetBrains March 2026
- Copilot Workspace preview launched April 2024; sunset May 30, 2025, and rebuilt into the Copilot coding agent (GA September 2025)
- License: Proprietary; VS Code Chat extension partially open-sourced in 2025

## Adoption
- 26M+ total users (Microsoft FY26 Q2 earnings, January 28, 2026)
- 4.7M+ paid subscribers (January 2026), up ~75% YoY
- ~140,000 organizations; ~90% of Fortune 100
- VS Code Marketplace: GitHub Copilot extension consistently the top AI extension; tens of millions of installs across the Copilot and Copilot Chat extensions
- ARR: not publicly disclosed; analyst estimates cluster around $700M–$2B depending on enterprise seat assumptions

## Architecture
- Model support: OpenAI GPT-4.1/5-class models, Anthropic Claude Sonnet/Opus, Google Gemini 2.5, plus Microsoft's own models — selectable per chat/agent session
- BYOK: Limited; Enterprise can bring approved model endpoints, but BYOK is not a core consumer feature
- Agent harness: "Agent mode" in VS Code Chat (multi-file edits, runs terminal commands, iterates against tests); Copilot coding agent on github.com (assigned to issues, opens PRs autonomously); Mission Control dashboard (late 2025) coordinates concurrent agent tasks
- MCP support: Yes — first-class MCP client in VS Code Chat since 2025
- Codebase indexing: Workspace context, semantic code search, repository-wide indexing for Copilot Enterprise

## Pricing
- Copilot Free: limited completions and chat
- Copilot Pro: $10/mo (300 premium requests, includes coding agent)
- Copilot Pro+: $39/mo (1,500 premium requests)
- Copilot Business: $19/user/mo
- Copilot Enterprise: $39/user/mo (includes knowledge bases, custom models)
- Moved to usage-based billing for premium model requests in 2025

## Differentiators
- Distribution: bundled with the world's dominant code host and editor
- Enterprise trust: SOC 2, data residency, Fortune 100 procurement already done
- Full agentic stack: in-editor agent + cloud coding agent + PR review + Mission Control
- Tightest integration with GitHub-native workflows (issues, PRs, Actions, code review)
- Multi-model menu without forcing users to manage keys

## See Also
- [[VSCode Ecosystem]]
- [[Cline]]
- [[Continue]]
- [[Cody]]
- [[JetBrains Junie]]
