---
tags: [tool, ide-extension, vscode, open-source, agent, byok]
created: 2026-05-28
---

# Cline

Cline (originally "Claude Dev") is the open-source AI coding agent that proved a VS Code extension could rival Cursor on autonomy without forking the editor. The user brings their own API key, Cline drives the agent loop — plan, edit, run, iterate — entirely in-editor, with every tool call surfaced for human approval. By May 2026 it has 61K+ GitHub stars, 5M+ installs across the VS Code Marketplace and Open VSX, and a $32M Series A from Emergence and Pace. It is the reference implementation of the "transparent BYOK agent" archetype.

## Origin
- Maker: Cline Inc., created by Saoud Rizwan; first released July 2024 as "Claude Dev"
- Renamed to Cline in early 2025 (VS Code extension ID still `saoudrizwan.claude-dev`)
- License: Apache 2.0
- Funding: $32M combined Seed + Series A announced July 31, 2025 (Emergence Capital, Pace Capital, 1984 Ventures, Essence VC, Cox Exponential; angels including Jared Friedman, Logan Kilpatrick, Addy Osmani, Eric Simons)

## Adoption
- 61,400+ GitHub stars, 6,400+ forks (verified May 2026)
- 5M+ combined installs across VS Code Marketplace and Open VSX Registry (May 2026)
- 297+ contributors

## Architecture
- Model support: 30+ providers — Anthropic Claude, OpenAI, Google Gemini, xAI Grok, OpenRouter, AWS Bedrock, Azure OpenAI, GCP Vertex, Mistral, DeepSeek, Ollama, LM Studio, and arbitrary OpenAI-compatible endpoints
- BYOK: Yes — the canonical BYOK agent; users pay the inference provider directly
- Agent harness: ReAct-style plan/act loop with explicit human-in-the-loop approval for every file edit, terminal command, and tool call; diff-based file editing
- MCP support: Yes — full MCP client, with a marketplace for installing community MCP servers from inside the extension
- Codebase indexing: Tree-sitter-based file mapping plus on-demand semantic search; no mandatory cloud index
- Extensibility: Rules, Hooks, Workflows, Skills (added through 2025–2026)

## Pricing
- Extension: free and open source
- BYOK direct-to-provider is the default — Cline takes no margin
- Cline Account: optional aggregated billing across providers
- Teams: $20/user/mo after Q1 2026, with 10 free seats included
- Enterprise: custom

## Differentiators
- Truly open source under Apache 2.0 — no proprietary dependency
- "Show every tool call" transparency: every edit and command is previewed and approved
- Provider-agnostic by design; user owns the spend
- MCP marketplace inside the extension lowered the cost of adding new tool capabilities
- Strong reputation among power users for not hiding the agent loop behind UI sugar

## See Also
- [[VSCode Ecosystem]]
- [[Roo Code]]
- [[Kilo Code]]
- [[Continue]]
- [[GitHub Copilot]]
