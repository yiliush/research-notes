---
tags: [tool, ide-extension, vscode, jetbrains, open-source, agent, byok]
created: 2026-05-28
---

# Continue

Continue is the longest-running open-source AI coding assistant for VS Code and JetBrains — predating Cline by more than a year — and has repositioned in 2025–2026 from "Copilot alternative" toward "source-controlled AI checks, enforceable in CI." Continue 1.0 (Feb 2025) consolidated chat, autocomplete, edit, and agent modes into a single extension with a config-as-code model (`config.yaml`) that lets teams version prompts, models, and tools alongside their code. 32K+ stars, 2.5M+ VS Code installs, $5M+ raised — a steady, technically respected player.

## Origin
- Maker: Continue Dev, Inc. — Y Combinator S23
- Launched July 2023; v1.0 released February 26, 2025
- License: Apache 2.0
- Funding: ~$5.1M total — $2.1M seed (Heavybit, led by Jesse Robbins; angels Julien Chaumond, Lisha Li, Florian Leibert), plus $3M SAFE round announced Feb 2025

## Adoption
- 32,400+ GitHub stars, 4,400+ forks (March 2026)
- 2.5M+ VS Code Marketplace installs (March 2026)
- JetBrains marketplace installs in the hundreds of thousands

## Architecture
- Model support: any provider via config — Anthropic, OpenAI, Gemini, Mistral, Cohere, Bedrock, Vertex, Ollama, LM Studio, vLLM, Together, OpenRouter, etc.
- BYOK: Yes — the original BYOK assistant; Team/Company plans add hosted BYOK with access controls
- Agent harness: chat, edit, autocomplete, and agent modes; agent mode is where MCP tools and multi-step workflows run
- MCP support: Yes — full MCP client supporting Resources, Prompts, and Tools; remote HTTP transports added in 2025
- Codebase indexing: local embedding index (configurable model), context providers (file, folder, terminal, problems, repo-map, web)
- Config-as-code: `config.yaml` is checked in alongside code; assistants and rules can be shared via continue.dev hub

## Pricing
- Solo: free (BYOK)
- Team: per-user pricing for shared assistants, rules, and policies
- Company: SSO, audit, BYOK, enterprise support
- Continue CLI and CI checks: included in paid tiers

## Differentiators
- Config-as-code: the assistant is a versioned artifact in the repo, not a SaaS setting
- "AI checks enforceable in CI" positioning — quality control, not just generation
- Dual VS Code + JetBrains support from day one
- Hub for sharing assistants, rules, and MCP server configs
- Highest provider/model breadth of any IDE extension; trivial to swap models

## See Also
- [[VSCode Ecosystem]]
- [[Cline]]
- [[Roo Code]]
- [[GitHub Copilot]]
- [[JetBrains Junie]]
