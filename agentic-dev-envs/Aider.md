---
tags: [tool, cli-agent, open-source, apache-2, indie, foundational]
created: 2026-05-28
---

# Aider

The original CLI coding agent and the project that invented diff-based code editing for LLMs. A solo-developer Python tool built by Paul Gauthier in 2023 — predating Claude Code by ~18 months — that established the conventions (unified diffs, git auto-commits, repo map context) every entry in this cluster now copies. Retains a strong cult following long after better-funded successors arrived.

## Origin
- First released **2023** by **Paul Gauthier** (independent; ex-CTO Groupon, ex-VP Eng Geomagical Labs, Dalhousie BSc CS '94, UW MS).
- Project transferred to the `Aider-AI/aider` org in 2024; original `paul-gauthier/aider` repo redirects.
- Latest release: **v0.86.0** (August 9, 2025). Active maintenance continued into March 2026.

## Architecture
- **Model support:** 100+ models — Claude (Opus 4, Sonnet 4, 3.7 Sonnet), OpenAI (o1, o3-mini, GPT-4o, GPT-5), DeepSeek R1/V3, Gemini 2.5, Mistral, plus any OpenAI-compatible endpoint and local models via Ollama.
- **Edit formats:** Aider invented and benchmarks several — `whole`, `diff`, `udiff`, `editor-diff`, `architect`. The `udiff` unified-diff format with line/context matching is its signature contribution; it dramatically reduced botched edits vs. whole-file rewrites.
- **Repo map:** Tree-sitter-based ranked symbol graph that fits the most relevant code into limited context windows. Predates and inspired similar features in Cursor, Claude Code, Codex.
- **Git-native:** Auto-commits every change with a generated message; `/undo`, `/diff`, `git revert` workflows are first-class.
- **Architect mode:** planner/editor split — a stronger model proposes, a cheaper one edits. Direct precursor to Claude Code's plan mode.
- **MCP:** Limited/community support — Aider predates MCP and remains more git-and-editor-centric than agent-orchestration-centric.
- **Voice input, image input, web scraping, linting/test loops** all built in.

## Distribution & Adoption
- License: **Apache 2.0**, fully open source.
- Install: `pip install aider-install` (preferred), `pipx install aider-chat`, or `python -m pip install -U aider-chat`.
- GitHub stars: **~45.5K** on `Aider-AI/aider` (May 2026), 4.5K forks.
- PyPI: **6.8M+ cumulative installs**.
- Telemetry from the project: ~15B tokens/week processed, top-20 OpenRouter app, self-reports 88% of new Aider code is written by Aider.

## Pricing
- Free, open source. Users pay only the underlying model provider for tokens.
- No hosted service, no telemetry phone-home by default.

## Differentiators
- **Invented diff-based editing** — the technique every other entry here uses descends from Aider's benchmarks.
- **Genuinely model-agnostic** — 100+ providers, no preferred-model lock-in, runs against local Ollama with no compromise in core features.
- **Git-as-state** — every action is a commit, every undo is `git revert`. No proprietary session format.
- **Solo developer, no VC** — pure community OSS in a category increasingly dominated by frontier-lab products.
- **Lowest distribution friction in cluster** for Python users: pip install and you're agent-coding in 30 seconds.

## See Also
- [[CLI Coding Agents]]
- [[Claude Code]]
- [[Codex CLI]]
- [[Goose]]
