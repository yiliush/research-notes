---
tags: [cluster, moc, ide-extension, vscode, jetbrains]
created: 2026-05-28
---

# VS Code Ecosystem

The VS Code extension surface is the single largest distribution channel for agentic development environments in 2026. Microsoft built the editor; every other player in this cluster — from Cline to Augment to Sourcegraph — sells against Microsoft on Microsoft's own substrate. The asymmetry is brutal and instructive: GitHub Copilot has ~26M users and 4.7M paid seats; the entire open-source long tail (Cline, Roo, Continue, Kilo) added together is in the tens of millions of installs but still a minority of paid spend. Yet the open-source agents are setting the technical pace — BYOK transparency, MCP tool ecosystems, multi-mode agents — and Copilot's product roadmap visibly tracks behind them.

## Platform dynamics

VS Code is open source (MIT) but the Marketplace, the Remote Development extensions, and key proprietary features are controlled by Microsoft. This creates three competitive postures:

1. **Microsoft's own play (Copilot)**: bundle distribution, enterprise procurement, multi-model menu without BYOK burden, agentic surface in chat and on github.com.
2. **Extensions competing on the substrate (Cline, Roo, Continue, Kilo, Augment, Tabnine, Cody, Qodo)**: ship into the same Marketplace, compete on agent capability, transparency, model choice, or vertical positioning (enterprise, quality, large codebases).
3. **Fork the editor entirely (Cursor, Windsurf, Trae)**: covered in a separate cluster — they share VS Code's UI conventions but escape Marketplace constraints.

JetBrains AI Assistant / Junie is the only major non-VS-Code agent in this cluster. It exists because JetBrains' ~17M users are a parallel distribution channel that Microsoft does not control.

## Players in this cluster

- [[GitHub Copilot]] — the incumbent. 26M users, 4.7M paid, $10–39/mo. Agent mode GA March 2026; coding agent GA September 2025.
- [[Cline]] — 61K stars, 5M+ installs, $32M raised, Apache 2.0. The canonical BYOK transparent agent.
- [[Roo Code]] — 22K stars, 1.2M installs, Apache 2.0. The successful fork of Cline; multi-mode agents.
- [[Continue]] — 32K stars, 2.5M installs, $5M raised, Apache 2.0. Config-as-code, VS Code + JetBrains, "AI checks in CI."
- [[Cody]] — Sourcegraph's enterprise code-graph play. Free/Pro discontinued July 2025; Cody Enterprise $59/user/mo; Amp is the new individual agentic tool.
- [[Tabnine]] — 9.4M VS Code installs, $102M raised, founded 2017. Enterprise compliance and air-gapped deployment specialist.
- [[Augment Code]] — $252M raised at ~$977M valuation. SWE-bench Pro #1. Built for 400K+-file codebases.
- [[Kilo Code]] — 17.5K stars, 1.5M+ users, MIT, $8M seed. 500+ BYOK models, Orchestrator multi-agent mode, VS Code + JetBrains.
- [[Qodo]] — (formerly CodiumAI). Quality-first: test generation and PR review. 682K VS Code + 492K JetBrains installs.
- [[JetBrains Junie]] — JetBrains' autonomous coding agent. GA Jan 2026. Claude Agent SDK integration Sept 2026. PSI-grounded context.

## Cross-cutting observations

- **BYOK is the open-source moat.** Cline, Roo, Continue, and Kilo all default to user-owned API keys. Copilot, Cody, Augment, and Tabnine do not. The OSS players are explicitly betting that developers will not tolerate margin-on-tokens once they understand it.
- **MCP is now table stakes.** Every player in this cluster ships an MCP client. The differentiation moved up the stack to which servers come bundled or curated.
- **Agent modes are converging on the same vocabulary.** Ask / Architect / Code / Debug appears across Roo, Kilo, and (less explicitly) Continue. Copilot's "agent mode" maps to the same primitive.
- **Codebase indexing is bifurcating.** OSS players use local tree-sitter + embeddings; enterprise players (Augment, Cody, Tabnine) build proprietary cloud indexes spanning monorepos, docs, and ticketing.
- **The funding gap is enormous.** Copilot (Microsoft) and Augment ($252M) are at one extreme; Cline ($32M), Kilo ($8M), Continue ($5M) are an order of magnitude smaller — and ship faster.

## Related clusters

- IDE forks (Cursor, Windsurf, Trae) — separate substrate, similar agent semantics
- CLI agents (Claude Code, Aider, Codex CLI, Gemini CLI) — terminal-native rather than IDE-native
- Cloud coding agents (Devin, Lovable, Replit Agent) — async, browser-first
