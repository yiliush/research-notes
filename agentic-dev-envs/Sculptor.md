---
tags: [tool, sandbox, imbue, open-source, parallel-agents, ade-cluster]
created: 2026-05-28
---

# Sculptor

Sculptor is Imbue's open-source desktop app for running parallel coding agents in isolated Docker containers on a developer's local machine. It is sandbox infrastructure aimed at the laptop, not the cloud — a different bet from E2B, Daytona, or Modal. Each agent task gets its own containerized copy of the repo so multiple agents (Claude Code, Cursor agents, Codex CLI, custom harnesses) can work side-by-side without stomping on each other's filesystem.

## Company / Origin
- Built by Imbue, the AI lab founded by Kanjun Qiu and Josh Albrecht (formerly Generally Intelligent, rebranded). Imbue raised a $200M round at $1B+ valuation in 2023 to train large language models for software-agent use cases.
- After Imbue's own model-training ambitions were dialed back in 2024–2025 (the foundation-model arms race got too expensive), the team refocused on agent tooling. Sculptor is one of the outputs.
- Repo: github.com/imbue-ai/sculptor, Apache 2.0.

## Architecture
- **Local Docker containers per agent task.** Each container is a fresh copy of the repo on a fresh git branch, with the agent harness mounted.
- Cached Docker images per project mean task startup is seconds, not minutes — Imbue published a blog post ("How we made sandboxed coding agents 10x faster to start") describing the snapshot and layer-cache tricks they use.
- Designed for the "parallel-agents on one laptop" workflow: kick off 5–10 attempts at a task simultaneously, review their diffs in a side-by-side UI, pick the best one.
- Not a cloud service — there is no Imbue-hosted control plane. State lives on disk; orchestration is a desktop app.
- MCP-native: Sculptor integrates with Claude Code and other MCP-speaking agents as the sandbox layer.

## Pricing
- Free, open-source. No hosted tier.
- Cost is the developer's own Docker / disk / CPU.

## Strategic Position
- Fits in the same "parallel agent orchestrator" category as [[Conductor]], [[Crystal]], [[Claude Squad]], [[uzi]], [[Container Use]] — see [[Parallel Agent Orchestrators]].
- The differentiator vs Container Use (Dagger's similar tool) is the desktop-app UI plus the deeper investment in startup-time optimization. Container Use is more of a CLI/MCP primitive; Sculptor is a full app.
- The structural question: is local containerized parallelism the right primitive, or do developers ultimately want cloud sandboxes (E2B / Daytona / Codex Cloud) so they can close the laptop? Sculptor's bet is that for the next several years, latency-sensitive iteration happens locally and developers will pay the disk/CPU cost for the privacy/speed tradeoff.
- Imbue's broader strategic question is whether tooling-only is enough revenue to sustain a lab — Sculptor is OSS with no monetization path stated as of May 2026.

## See Also
- [[Cloud Sandboxes]] — concept
- [[Parallel Agent Orchestrators]] — adjacent cluster
- [[Container Use]] — closest direct comparison (Dagger)
- [[Conductor]]
- [[Crystal]]
- [[Claude Squad]]
- [[uzi]]
- [[Claude Code]] — primary integration target
- [[Devcontainers]]
