---
tags: [tool, cli-agent, open-source, mit, go, charm, terminal-aesthetic]
created: 2026-05-28
---

# Crush

Charmbracelet's terminal-first agentic coding tool — the prettiest CLI agent in the cluster and the only one whose primary selling point is developer delight. A Go binary built on the same Charm TUI stack that powers 25K+ terminal applications, MIT-licensed, model-agnostic, and aggressively portable.

## Origin
- Released **August 2025** by **Charmbracelet** — the team behind Bubble Tea, Lip Gloss, Glamour, Gum, Glow, and the broader Charm TUI ecosystem.
- Written in **Go**.
- Active release cadence: v0.13 through v0.73+ between launch and May 2026.

## Architecture
- **Model support:** OpenAI, Anthropic, Google Gemini, Groq, OpenRouter, Vercel AI Gateway, Azure OpenAI, AWS Bedrock, plus any OpenAI- or Anthropic-compatible endpoint. Provider list maintained in a community-curated companion repo (`catwalk`).
- **Session-preserving model swap:** swap providers mid-session without losing context — unique in the cluster.
- **LSP integration:** queries `gopls`, `rust-analyzer`, `pyright`, etc. for live symbol tables, diagnostics, and docs. Few other CLI agents talk to LSPs directly; most rely on the model to infer structure.
- **MCP:** supports HTTP, stdio, and SSE transports — most complete MCP transport coverage in the cluster.
- **Sandboxing:** standard permission prompts; no OS-level sandbox.
- **TUI:** built on Charm's Bubble Tea/Lip Gloss — the most polished terminal UI of any agent here.

## Distribution & Adoption
- License: **MIT** — most permissive in the cluster.
- Install: Homebrew, npm, Arch (AUR), Nix, Winget, Scoop, FreeBSD ports.
- Platforms: macOS, Linux, Windows (PowerShell + WSL), Android, FreeBSD, OpenBSD, NetBSD — widest OS support in the cluster.
- GitHub stars: **~24.8K** on `charmbracelet/crush` (May 2026).

## Pricing
- Free, fully open source. Users pay model providers directly.
- No hosted service.

## Differentiators
- **LSP-aware** — uniquely talks to language servers for ground-truth symbol info rather than relying entirely on model inference.
- **Mid-session provider swap** — preserves thread state across model changes; no other tool in the cluster does this cleanly.
- **Widest platform matrix** — runs on BSDs and Android, not just the macOS/Linux/Windows trinity.
- **MIT license** — more permissive than the Apache 2.0 used by Aider/Codex/Goose/Gemini CLI.
- **Charm ecosystem halo** — inherits trust and aesthetic from a team developers already love.
- Differentiates on **craft** in a category increasingly dominated by frontier-lab budgets — the open-source counterpart to Warp's pixel-perfect terminal.

## See Also
- [[CLI Coding Agents]]
- [[Aider]]
- [[Goose]]
- [[Warp]]
