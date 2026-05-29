---
tags: [company, ai-ide, zed, open-source, rust, ade-cluster]
created: 2026-05-28
---

# Zed

Zed is the AI-native code editor built from scratch in Rust by the original Atom and Tree-sitter team. It is the only entrant in this cluster that is not a VS Code fork — its custom GPU-accelerated UI engine and aggressive performance ceiling make it the structural alternative to the Electron-based incumbents (Cursor, Windsurf, VS Code itself). In 2025 Zed pivoted hard into agentic AI while remaining open source, and its Agent Client Protocol (ACP) is becoming a de facto standard for connecting external coding agents (Claude Code, Codex CLI, etc.) into any compatible editor.

## Company
- Founded 2021 by Nathan Sobo, Max Brunsfeld, and Antonio Scandurra — all veterans of GitHub's Atom team.
  - Sobo: one of the first two engineers on Atom (joined GitHub 2011), Electron co-creator
  - Brunsfeld: created Tree-sitter (now powers GitHub's code search infra)
  - Scandurra: co-architected Teletype, Atom's collaborative editing
- HQ: distributed/remote; legal entity in the US
- Funding (verified May 2026):
  - Seed 2021: ~$2.5M
  - Series A, Mar 2023: $10M led by Redpoint Ventures (total funding $12.5M)
  - Series B, Aug 2025: $32M led by Sequoia Capital — total raised >$42M. Returning: Redpoint, Root, Matchstick, V1.VC. Angels: Dylan Field (Figma), Tom Preston-Werner (GitHub), Spencer Kimball (CockroachDB), Rahul Vohra (Superhuman)
- Headcount: small (~25–40 estimated, no public count). Hires through GitHub-contributions pipeline ("Hired Through GitHub" series on their blog).

## Product
- Editor architecture: Rust, custom GPU-accelerated UI framework (GPUI). No Electron. Sub-millisecond input latency is the headline pitch.
- Zed 1.0 released April 2026 — first stable release.
- Indexing/retrieval: tree-sitter-based structural index. The "Agent Panel" supports semantic search via embeddings as a plug-in capability rather than a central pillar — Zed leans more on letting external agents bring their own retrieval.
- Model selection / routing: pluggable. Native support for Claude (Opus, Sonnet), GPT-5, Gemini, plus unlimited local Ollama models. Bring-your-own-API-key option.
- Key features:
  - Agent Panel — chat, inline edit, multi-file editing, parallel agents
  - Edit Prediction (Zeta2 open-weight model, in-house) — Tab-style next-edit suggestion
  - Real-time multiplayer collaboration (the original USP, predates AI focus)
  - DeltaDB (announced with Series B) — collaborative data layer for live agent/human cooperation
  - Agent Client Protocol (ACP) — open spec for embedding any external CLI agent (Claude Code, Codex, OpenCode) into Zed; positioned as the "MCP for editors"
  - GPU-accelerated terminal, native git, vim mode

## Pricing
Current tiers as of May 2026:
- Free: full editor (open source), 50 Zed-hosted AI prompts/month, unlimited local Ollama, unlimited edit prediction with own API key, full real-time collab, macOS/Linux/Windows
- Pro: $20/month — 500 Zed-hosted prompts/month, $5 token credit for usage-based billing, unlimited accepted edit predictions, priority access to frontier models (Claude Opus, GPT-5.4 Pro)
- Usage-based billing for prompts beyond included quota
- No published Teams/Enterprise tier as of May 2026

## Traction
- GitHub: zed-industries/zed at ~83.3K–83.4K stars as of May 20–21, 2026 (verified via web search)
- 150,000+ active developers; 1,100+ contributors since open-sourcing in Jan 2024
- Target of 100,000 active users by 2026 set at Series B — already exceeded
- No public ARR. Series B implies subscription revenue still modest relative to the cluster leaders.

## Strategic Position
- Distinctive moat: the only credible non-Electron editor in this category. Performance ceiling matters to a vocal segment of professional engineers (the "I hate VS Code's latency" cohort) — small as a market but high in influence.
- Open-source posture (editor, Zeta2 model, ACP protocol) buys credibility and contributor flywheel that Cursor/Windsurf cannot match. Conversely, monetization is harder — Zed has not shown anything like the ARR ramp Cursor or Replit have.
- ACP is the most strategically interesting bet: if it becomes the standard for embedding external agents, Zed positions itself as neutral runtime for the agent CLI ecosystem (Anthropic's Claude Code, OpenAI's Codex, etc.) — useful even to users who would never switch from VS Code.
- Realistically not competing with Cursor on enterprise revenue. Competing for mindshare, dev-tool credibility, and a long-tail bet that the editor stack itself matters once agents do most editing.

## See Also
- [[Cursor]] — the VS-Code-fork hyperscaler, opposite philosophy
- [[Windsurf]]
- [[Replit]]
- [[Trae]]
- [[AI-Native IDEs]]
- [[Agent Harness]]
- [[Codebase Indexing]]
- [[Market Landscape]]
