---
tags: [company/deepwisdom, async-agent, autonomous-coding, multi-agent, mgx, metagpt]
created: 2026-05-28
---

# MGX

MGX (MetaGPT X) is a multi-agent natural-language software development platform from DeepWisdom, the team behind the MetaGPT open-source framework. Launched February 2025, it simulates a full development team — product manager, architect, engineer, data analyst — collaborating to turn natural-language prompts into running software. By 2026 it began rebranding to "Atoms".

## Background

- **Maker:** DeepWisdom (deepwisdom.ai), the company behind MetaGPT.
- **Open-source roots:** MetaGPT, the open-source multi-agent framework, predates MGX. The repo (FoundationAgents/MetaGPT) is a foundational text in the multi-agent coding literature.
- **MGX launch:** February 19, 2025 — "world's first AI agent development team".
- **Product Hunt:** #1 Product of the Day, March 2025.
- **Rebrand:** Transitioning to "Atoms" / "Vibe Business Team" branding through 2026.

## Funding & Traction

- **Funding:** DeepWisdom is China-headquartered; specific Series funding details from US sources are limited. Backed by Chinese AI investors.
- **MetaGPT GitHub:** The open-source MetaGPT repo has 40k+ stars (one of the most-starred multi-agent frameworks on GitHub).
- **MGX traction:** Vendor-reported strong engagement post-launch; no audited user numbers public.

## Architecture

- **Multi-agent role-play.** Specialized agents play software-team roles: PM (requirements/spec), architect (design), engineer (code), data analyst (analytics). They collaborate via structured messages.
- **Natural-language input → runnable software.** "Vibe coding" — describe what you want, agents handle UI, code, infra, deployment.
- **Use cases:** Web apps, dashboards, data visualizations, mini-games, internal tools.
- **Async, sandboxed execution.** Generates a complete project in cloud sandbox, deployable from the UI.
- **SWE-bench:** MGX does not lead on SWE-bench Verified — it's optimized for greenfield generation (prompt → app), not for resolving issues against existing large repos.

## Pricing / Access

- **Freemium SaaS** on mgx.dev. Credit-based paid plans for higher generation limits.
- **Open-source counterpart:** MetaGPT framework remains free (MIT license) — self-host the multi-agent framework if you want full control.

## Differentiators

- **Multi-agent first.** Most cluster peers (Devin, Jules, Codex, Copilot agent) are single-agent loops. MGX is built around role specialization as the architectural primitive.
- **Greenfield-optimized.** Strong on "build me an app from scratch", weaker on "resolve this issue in a 100k-LOC monorepo".
- **Vibe-coding positioning.** Targets non-engineers and indie founders rather than enterprise dev teams — different ICP than Devin/Factory.
- **Open-source heritage.** MetaGPT's 40k-star OSS framework gives credibility and a community pipeline.
- **China origin.** One of few credible non-US entrants in the autonomous coding agent cluster.

## See Also

- [[Autonomous Coding Agents]]
- [[Devin]]
- [[Devika]]
- [[OpenHands]]
- [[MetaGPT]] — the open-source framework
