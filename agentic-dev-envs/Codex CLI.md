---
tags: [tool, cli-agent, open-source, apache-2, openai, rust]
created: 2026-05-28
---

# Codex CLI

OpenAI's open-source answer to Claude Code: a Rust-native terminal coding agent shipped under Apache 2.0. Originally a TypeScript prototype in April 2025, rewritten to Rust by mid-2025 for OS-level sandboxing and startup performance. Now the most-starred CLI agent on GitHub.

## Origin
- Launched **April 2025** as a TypeScript/Node terminal agent.
- Rewritten to Rust ("codex-rs") starting **June 2025**; 94.9% Rust, ~70 crates in a Cargo workspace.
- Built by OpenAI; ships natively for macOS (Apple Silicon/x86_64), Linux (x86_64/arm64), Windows.
- Latest release as of late May 2026: **v0.134.0** (May 26, 2026); 696+ releases total.

## Architecture
- **Model support:** ChatGPT account auth or OpenAI API key. GPT-5 family with 272K default context. Defaults to GPT-5.4 in 2026 builds.
- **Session model:** three primitives — Thread (persistent SQLite-backed conversation, resumable/forkable/archivable), Turn (one user→model round-trip), Item (granular events within a turn).
- **Sandboxing:** OS-level. Apple Seatbelt on macOS, Landlock + seccomp on Linux. `--sandbox` flag picks `read-only`, `workspace-write`, or `danger-full-access`. `~/.codex/memories` is included as a writable root in workspace-write.
- **MCP:** Both client and server. `codex mcp-server` exposes Codex as a tool to other agents (e.g., Claude Code calling Codex); inverse also supported.
- **Concurrent tool calls:** Rust runtime executes eligible MCP calls in parallel.
- **Memory:** Persistent SQLite threads survive process restarts.

## Distribution & Adoption
- License: **Apache 2.0**, fully open source.
- Install: `npm install -g @openai/codex`, `brew install --cask codex`, `curl chatgpt.com/codex/install.sh | sh`, or binary download.
- GitHub stars: **~86.6K** on `openai/codex` (May 2026), up from ~74K in April 2026.
- Usage: OpenAI reports 4M+ weekly developers.

## Pricing
- Free with a ChatGPT Plus/Pro/Business subscription (ChatGPT-account auth shares the subscription's compute budget).
- Or pay-as-you-go via OpenAI API key for the underlying model tokens.
- The CLI binary itself is free.

## Differentiators
- **Rust + OS sandboxing** — the only CLI agent here with native Seatbelt/Landlock integration, not just permission prompts.
- **MCP server mode** — Codex is uniquely designed to be both a top-level driver and a sub-tool of other agents.
- **Persistent SQLite threads** — fork/archive/rollback semantics are a step beyond ephemeral session files.
- **OpenAI distribution muscle** — ships with ChatGPT subscriptions, giving it instant reach Aider and Crush can't match.
- Open source under Apache 2.0 — same license as Aider/Goose/Gemini CLI, unlike Claude Code's source-available license.

## See Also
- [[CLI Coding Agents]]
- [[Claude Code]]
- [[Aider]]
- [[Gemini CLI]]
