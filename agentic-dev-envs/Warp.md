---
tags: [tool, cli-agent, proprietary, terminal, ade, vc-backed]
created: 2026-05-28
---

# Warp

The only entry in this cluster that started as a terminal and grew an agent — not an agent that pretends to be a terminal. Warp Agent Mode (June 2024) turned Zach Lloyd's Rust-based modern terminal into an agentic surface; Warp 2.0 (June 2025) rebranded the whole product as "the Agentic Development Environment" and added multi-threaded agents, code review panes, and a file editor inside the terminal.

## Origin
- Warp founded **June 2020** by **Zach Lloyd** (ex-Google Docs, ex-Time). Public macOS release **April 2022**.
- Linux support 2024; Windows support 2025.
- **Agent Mode** launched **June 2024** — AI executes commands directly in the shell, with confirm-before-write semantics.
- **Warp 2.0** launched **June 2025** — branded as the first Agentic Development Environment; added Code, Agents, Terminal, Drive as unified surfaces.
- Backed by Sequoia, GV.

## Architecture
- **Model support:** Multi-provider under the hood (Anthropic, OpenAI, Google); user-facing model selection plus BYOK as of May 2026.
- **Agent surface:** runs commands inline in the same shell you type into, not in a side panel. Confirm-before-destructive enforced.
- **Multi-threaded agents:** run multiple agents in parallel, monitor via a management UI, get notifications on completion or blocking.
- **Code surface:** lightweight in-terminal file editor with tabs, file tree, syntax highlighting, and a dedicated diff/review panel for agent changes.
- **Warp Drive:** team-shared knowledge store for commands, notebooks, env vars, prompts, MCP config, rules.
- **MCP:** first-class. MCP servers configured at the Drive level apply to both humans and agents.
- **Benchmarks:** #1 on Terminal-Bench (52%), top-5 on SWE-bench Verified (71% at launch, 75.8% with GPT-5 by September 2025).
- **Cloud agents:** "Oz" cloud agent runs available on Enterprise.

## Distribution & Adoption
- License: **proprietary**, closed source. Native Rust binary.
- Platforms: macOS, Linux, Windows.
- Install: signed installers from warp.dev; Homebrew cask.
- No public star count (closed source). VC-backed adoption metrics not public, but Sequoia and Fast Company coverage suggest large indie/startup user base.

## Pricing
- **Free** — $0/mo, 75 AI credits/mo after a 150-credit two-month onboarding.
- **Build** — **$20/mo**, 1,500 credits, BYOK, 40-repo codebase context, Drive, collaboration.
- **Business** — **$50/mo**, adds SAML SSO, team-wide ZDR, up to 50 seats.
- **Enterprise** — **$200/mo tier** discussed in press for advanced agent platform features; custom for unlimited seats, dedicated support, Oz cloud agents.
- BYOK available on all plans as of May 21, 2026 (Free included).
- Platform-credits billing in preview through June 30, 2026; metering begins July 1, 2026.

## Differentiators
- **Terminal-first, not agent-first** — the agent inhabits the same shell you already use; doesn't run in a sub-pane or wrapper.
- **Multi-threaded agents with a UI** — Warp ships the most developed parallel-agent management surface in the cluster.
- **Benchmark leadership** on Terminal-Bench (which Warp's positioning relies on).
- **The "ADE" framing** — coined by Warp; the rest of this research vault is organized around their term.
- **Closed source + proprietary terminal** — only entry where the terminal itself is a moat, not just the agent on top of it.
- Beautiful, modern terminal UX as the wedge — the polished, monetizable counterpart to Crush.

## See Also
- [[CLI Coding Agents]]
- [[Crush]]
- [[Claude Code]]
