---
tags: [tool, ide-extension, vscode, open-source, agent, fork, byok]
created: 2026-05-28
---

# Roo Code

Roo Code is the most successful fork of Cline — a community-driven open-source agent that diverged in late 2024 to ship faster on features Cline was slower to adopt: custom modes, diff-based editing, role-specific personas, and a community-curated Mode Gallery. By May 2026 it has 22K+ GitHub stars, ~1.2M VS Code installs, and a contributor base (~300) on par with the original. The Roo vs. Cline split is the canonical example of how permissive licenses turn one project into a competitive substrate.

## Origin
- Maker: RooCodeInc community fork (formerly "Roo Cline"), forked from Cline late 2024
- License: Apache 2.0 (inherited from Cline)
- Funding: community-led; no disclosed institutional round as of May 2026

## Adoption
- 22K+ GitHub stars (May 2026)
- ~1.2M VS Code Marketplace installs (February 2026, extension ID `RooVeterinaryInc.roo-cline`)
- 300+ contributors

## Architecture
- Model support: Same broad BYOK provider surface as Cline (Anthropic, OpenAI, Gemini, xAI, OpenRouter, Bedrock, Vertex, local models)
- BYOK: Yes — users connect their own API keys
- Agent harness: Multi-mode system — Code, Architect, Ask, Debug, and Custom modes. Each mode has scoped tool permissions and a tailored system prompt
- Custom Modes: user-defined AI personas; community Mode Gallery shares pre-tested configurations (React dev, docs writer, security review, testing)
- MCP support: Yes — MCP client compatible with Cline's ecosystem
- Diff-based file editing (a core fork differentiator from early Cline)
- Codebase indexing: tree-sitter file maps, ripgrep-style search

## Pricing
- Extension: free and open source
- BYOK direct-to-provider; Roo takes no margin
- Optional Roo Code Cloud: cloud agents for GitHub, web, and Slack workflows (pricing per usage)

## Differentiators
- Multi-modal agents: mode switching as a first-class UX, with scoped permissions per mode
- Community Mode Gallery: distribution channel for prompt+tool bundles
- Faster feature iteration than Cline through 2025 (custom modes, multi-agent personas shipped first here)
- Cloud agents extending the in-editor agent to async surfaces (GitHub, web, Slack)
- Same codebase trust model as Cline — every tool call visible

## See Also
- [[VSCode Ecosystem]]
- [[Cline]]
- [[Kilo Code]]
- [[Continue]]
