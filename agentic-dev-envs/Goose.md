---
tags: [tool, cli-agent, open-source, apache-2, framework, linux-foundation]
created: 2026-05-28
---

# Goose

Block's open-source, model-agnostic agent framework — not just a CLI, but a runtime that ships as both a Desktop app and a terminal binary. Built around MCP from day one, donated to the Linux Foundation's Agentic AI Foundation in 2026, and positioned more as a general agent platform that happens to code than as a coding-specific tool.

## Origin
- Launched **January 2025** by **Block** (formerly Square) as `codename goose`.
- Repo moved from `block/goose` to `aaif-goose/goose` under the **Linux Foundation's Agentic AI Foundation (AAIF)** in 2026.
- Latest release: **v1.36.0** (May 27, 2026); 136 total releases.
- Stack: Rust core (63%) + TypeScript UI (30%).

## Architecture
- **Model support:** 15+ providers — Anthropic, OpenAI, Google, Ollama, OpenRouter, Azure, AWS Bedrock, Databricks, plus more. ACP support lets users wire existing subscriptions.
- **Two surfaces:** native Desktop apps (macOS, Linux, Windows) and full CLI — both share the same Rust core and extension model.
- **Extensions = MCP servers.** Goose was an MCP early adopter; 70+ extensions cover databases, browsers, GitHub, Google Drive, JetBrains, Figma. The extension catalog is the de facto "skills" system.
- **Recipes:** YAML-defined reusable agent workflows. Closer to Claude Code's skills than to its hooks.
- **Goose-to-Goose:** Desktop and CLI instances can hand off to each other — a primitive form of agent collaboration.
- **No proprietary sandbox** — relies on host OS permissions and user confirmation.

## Distribution & Adoption
- License: **Apache 2.0**.
- Install: `curl ...download_cli.sh | bash` for CLI; signed installers for Desktop.
- GitHub stars: **~46K** on `aaif-goose/goose` (May 2026), 4.7K forks, 350+ contributors.
- Adoption is enterprise-skewed — Block uses it internally; Databricks featured it at Data+AI Summit 2025.

## Pricing
- Free, fully open source. Users pay model providers directly for tokens.
- No hosted offering from Block — it's a true framework, not a SaaS.

## Differentiators
- **Desktop + CLI parity** — only entry in this cluster with a first-class native GUI app sharing the same core.
- **MCP-first design** — Goose has more catalog-style MCP extensions wired up out-of-the-box than any peer.
- **Linux Foundation governance** — the only major CLI agent under neutral foundation governance, attractive to enterprises wary of vendor capture.
- **Framework framing** — positioned to automate broader workflows (data ops, ticketing, infra) not just code editing. Closest to a "generic on-machine agent" in the cluster.
- **Rust core** — matches Codex CLI on the performance/memory-safety axis.

## See Also
- [[CLI Coding Agents]]
- [[Claude Code]]
- [[Codex CLI]]
- [[Aider]]
