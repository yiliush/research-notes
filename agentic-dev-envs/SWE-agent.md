---
tags: [academic, async-agent, autonomous-coding, open-source, swe-bench, princeton]
created: 2026-05-28
---

# SWE-agent

SWE-agent is the Princeton/Stanford academic project that introduced the "agent-computer interface" idea and produced the original SWE-bench. It's the academic anchor of the async-agent cluster — small, sharp, research-driven, and quietly held a SOTA position on SWE-bench during 2024–early 2025.

## Background

- **Origin:** Princeton University NLP group, with Stanford collaborators. NeurIPS 2024 paper.
- **Authors:** John Yang, Carlos E. Jimenez, Alexander Wettig, Kilian Lieret, Shunyu Yao, Karthik Narasimhan, Ofir Press.
- **Companion project:** The same group built SWE-bench — the GitHub-issue benchmark that became the de facto yardstick for the entire cluster.
- **Relationship to OpenHands:** Distinct project, similar lineage. SWE-agent is the minimal research scaffold; OpenHands is the productized open platform.

## Funding & Traction

- **Funding:** Academic — Princeton, Stanford grants; no startup funding.
- **GitHub:** ~19.3k stars on the main SWE-agent repo (late 2025).
- **Family of projects:**
  - **SWE-agent** — the original scaffold.
  - **mini-swe-agent** — ~100 lines of Python that scores >74% on SWE-bench Verified.
  - **SWE-smith** (NeurIPS 2025 D&B Spotlight) — scaling training data for SWE-agents; produced SWE-agent-LM-32B with 40.2% pass@1 on SWE-bench Verified.

## Architecture

- **Agent-Computer Interface (ACI):** The paper's central contribution. Custom terminal commands designed for LLMs (file viewer with paging, syntax checking on edit, scoped search). The insight: agents do better with a curated tool surface than with raw bash.
- **Single-agent loop.** ReAct-style: observe → think → act → observe. No multi-agent orchestration.
- **Model-agnostic.** Works with any LM via API.
- **Trajectory dataset.** SWE-smith released 26k SWE-agent trajectories — training fuel for the next generation of agents.
- **SWE-bench Verified:**
  - SWE-agent 1.0 + Claude 3.7: SOTA on SWE-bench full and lite as of February 28, 2025.
  - mini-swe-agent: >74% on SWE-bench Verified in ~100 lines.
  - SWE-agent-LM-32B (trained on SWE-smith data): 40.2% pass@1.

## Pricing / Access

- **Free, open source** (MIT license).
- **Self-hosted.** Bring-your-own LLM API key.

## Differentiators

- **Academic rigor.** Peer-reviewed (NeurIPS 2024, NeurIPS 2025), reproducible, instrumented for research.
- **Minimal scaffold.** mini-swe-agent's ~100 lines + 74% Verified score is an indictment of every overengineered commercial harness in this cluster.
- **Owns the benchmark.** The same group built SWE-bench; their agent designs naturally exercise the benchmark cleanly.
- **Training data factory.** SWE-smith's trajectory dataset enables open-model post-training for agentic coding — used by downstream open-source efforts.
- **Pure research stance.** No enterprise GTM, no acquisition rumors. Just papers and code.

## See Also

- [[Autonomous Coding Agents]]
- [[SWE-bench Verified]]
- [[OpenHands]]
- [[Devika]]
- [[Codex Cloud]]
