---
tags: [tool, ide-extension, vscode, jetbrains, open-source, agent, byok]
created: 2026-05-28
---

# Kilo Code

Kilo Code is the third major open-source agent in the Cline/Roo lineage — explicitly positioned as "the all-in-one agentic engineering platform" with the broadest BYOK model menu in the cluster (500+ models) and a multi-mode agent system that borrows from Roo. By May 2026 it has 17.5K GitHub stars, 1.5M+ users, $8M seed funding, and a JetBrains plugin in addition to its VS Code extension. Distinguishes itself by paying down the orchestration story — Architect/Code/Debug/Ask/Custom/Orchestrator — instead of just providing a chat UI.

## Origin
- Maker: Kilo-Org / kilo.ai, OSS project incorporated as a company
- Forked/inspired by Cline and Roo Code lineage
- License: MIT
- Funding: $8M seed round (disclosed prior to May 2026)

## Adoption
- 17,500+ GitHub stars (May 2026; some sources report ~16,200)
- 1.5M+ users (company-reported); some sources cite 3M+
- 30T+ tokens processed (company-reported)
- VS Code Marketplace listing as `kilocode.Kilo-Code`; JetBrains plugin available

## Architecture
- Model support: 500+ BYOK models — Anthropic, OpenAI, Gemini, xAI, OpenRouter, Bedrock, Vertex, DeepSeek, Mistral, local Ollama/LM Studio, etc.
- BYOK: Yes — direct provider keys or aggregated Kilo billing
- Agent harness: six modes — Ask (read-only Q&A), Architect (plan), Code (autonomous implementation with file writes and shell), Debug (test/error triage), Custom (user-defined), Orchestrator (coordinates multiple agents in parallel)
- MCP support: Yes
- Codebase indexing: tree-sitter file maps, codebase search; optional indexing
- Surfaces: VS Code, JetBrains, CLI

## Pricing
- Extension: free and open source
- BYOK direct to provider
- Optional aggregated Kilo billing for convenience

## Differentiators
- Orchestrator mode: parallel sub-agent coordination as a built-in primitive (the closest in-extension analog to Claude Code's subagent model)
- Largest BYOK model menu in this cluster (500+)
- JetBrains plugin parity with VS Code — most Cline forks are VS Code only
- MIT license (vs. Apache 2.0 for Cline/Roo/Continue) — slightly more permissive
- Positions explicitly as a "platform," not an extension

## See Also
- [[VSCode Ecosystem]]
- [[Cline]]
- [[Roo Code]]
- [[Continue]]
- [[JetBrains Junie]]
