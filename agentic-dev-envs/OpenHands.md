---
tags: [company/all-hands-ai, async-agent, autonomous-coding, open-source, openhands]
created: 2026-05-28
---

# OpenHands

OpenHands is the open-source autonomous software engineering platform that took the "Devin clone" mantle after the original OpenDevin project rebranded in late 2024. Backed by All Hands AI and built around the CodeAct framework, it's the leading self-hostable async agent — 71k+ stars, MIT licensed, model-agnostic.

## Background

- **Maker:** All Hands AI, the company spun out to commercialize the project.
- **Origin:** Started as **OpenDevin** in March 2024 by Xingyao Wang and collaborators, explicitly to replicate Cognition's Devin in the open.
- **Rebrand:** Renamed to OpenHands in late 2024 under the All-Hands-AI GitHub org. Dropped "Devin" framing as the project's ambitions outgrew clone status.
- **Research:** "OpenHands: An Open Platform for AI Software Developers as Generalist Agents" published as an ICLR 2025 conference paper.

## Funding & Traction

- **Series A (2024–2025):** $18.8M raised by All Hands AI.
- **GitHub:** 71k+ stars as of late 2025 (project blog: "One Year of OpenHands", Nov 12, 2025). ~500 contributors.
- **Anniversary milestone:** One-year retrospective (Nov 2025) documented dozens of LLM providers supported, hundreds of contributors, and broad community deployment.
- **License:** MIT — the broadest permissive license in this cluster.

## Architecture

- **Local-first execution.** Runs in Docker on the user's machine; cloud deployment is optional (All Hands offers a hosted variant).
- **CodeAct framework.** Agent acts by emitting executable Python/bash that runs in a sandbox, observing output, and iterating. State-of-the-art open-source approach to agent tool use.
- **Multi-agent capable.** Different agents for planning, execution, browsing; orchestratable.
- **Model-agnostic.** Supports dozens of LLM providers (Anthropic, OpenAI, Google, local Ollama, vLLM, etc.).
- **Software Agent SDK.** OpenHands evolved past a single product into an SDK for building agent applications.
- **SWE-bench Verified:**
  - OpenHands + strong model: ~53% baseline, up to ~77.6% with CodeAct 2.1 + frontier models. SOTA open-source as of late 2025.

## Pricing / Access

- **Open source / self-hosted:** Free, MIT licensed. Bring-your-own model API keys (and pay those costs).
- **All Hands Cloud:** Hosted version with managed sandbox and model access. Subscription-based; pricing on the All Hands AI site.

## Differentiators

- **Open-source dominance.** 71k+ stars makes OpenHands the unambiguous leader of the open-source async-agent category. Devika (~19.5k, mostly inactive) and SWE-agent (~19k, academic) are well behind.
- **Self-hostable.** The only credible answer for enterprises that can't ship code to Cognition's, OpenAI's, or Google's clouds.
- **Model-agnostic.** Customers pick their model. Frontier-lab agents are locked to one vendor.
- **CodeAct.** The execute-Python-and-observe pattern is technically among the cleanest in the cluster and is widely cited in agent research.
- **SDK pivot.** OpenHands as a platform/SDK rather than a fixed product means it can host the next paradigm shift (multi-agent orchestration, voice, etc.) without re-architecting.
- **Active research org.** ICLR paper + dozens of follow-on papers cite or extend OpenHands.

## See Also

- [[Autonomous Coding Agents]]
- [[Devin]] — the proprietary competitor it was built to challenge
- [[Devika]] — the other Devin clone, now dormant
- [[SWE-agent]] — academic cousin
- [[Codex Cloud]] — closest proprietary analog
