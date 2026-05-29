---
tags: [open-source, async-agent, autonomous-coding, devin-clone, devika, dormant]
created: 2026-05-28
---

# Devika

Devika was the first open-source "Devin clone" — a March 2024 hackathon-style project by a 21-year-old developer in Kerala, India, built in roughly 20 hours during the original Devin hype wave. It briefly hit ~19.5k GitHub stars and 2.6k forks before momentum stalled; by 2025 the project was largely dormant, with the OpenHands rebrand absorbing most of the open-source-Devin energy.

## Background

- **Creator:** Mufeed VH, founder of Lyminal and Stition.AI, based in Kerala, India.
- **Repository:** stitionai/devika on GitHub.
- **Origin:** Launched March 2024, days after Cognition's Devin demo went viral. Explicit goal: open-source alternative aiming at Devin's SWE-bench numbers.
- **Tagline:** "Agentic AI Software Engineer" — understand high-level instructions, plan, research, code.
- **Successor:** The creator has been working on a follow-up/rebrand referenced as "Opcode" in some sources.

## Funding & Traction

- **Funding:** None — solo developer / community project.
- **GitHub stars:** ~19.5k stars, 2.6k forks as of late 2025.
- **Activity:** A "Is this project abandoned?" issue was opened March 1, 2025, signaling community concern. Last meaningful updates around September 2025.
- **Practical status:** Largely dormant relative to OpenHands' 71k stars + 500 contributors. Devika is the historical clone; OpenHands is the live one.

## Architecture

- **Multi-LLM support.** Claude 3, GPT-4, Gemini, Mistral, Groq, local LLMs via Ollama.
- **Agentic loop.** Planning + reasoning, contextual keyword extraction for focused research, web browsing for information gathering, code generation, dynamic state tracking.
- **Local-first.** Self-hosted; bring-your-own model API keys.
- **Chat UI.** Natural-language interaction with agent-state visualization.
- **SWE-bench:** No published Verified score. The project's stated SWE-bench ambition was never achieved.

## Pricing / Access

- **Free, open source.** MIT-style license.
- **Self-hosted only.** No managed hosted offering.

## Differentiators

- **Historical first-mover.** Devika is the canonical Devin clone — the project that proved an open-source response was possible within days of Devin's launch.
- **Single-developer credibility.** Built solo in ~20 hours, then maintained part-time. Demonstrates how cheap the agent loop became once the pattern was visible.
- **Model breadth.** One of the earliest agents to support local Ollama models, which mattered for self-hosters wary of frontier API costs.

## Why it's effectively superseded

- **OpenHands ate its lunch.** OpenDevin (now OpenHands) absorbed most of the open-source-Devin community energy by late 2024.
- **No commercial GTM.** Solo creator, no team, no fundraise — couldn't keep pace with All Hands AI's $18.8M Series A.
- **Benchmark gap.** Never produced a published SWE-bench Verified number competitive with proprietary or other open agents.
- **Maintenance friction.** Solo maintainers don't scale; PR backlog and issue triage stalled by mid-2025.

## See Also

- [[Autonomous Coding Agents]]
- [[OpenHands]] — the open-source successor in the wild
- [[Devin]] — the original it was cloning
- [[SWE-agent]]
