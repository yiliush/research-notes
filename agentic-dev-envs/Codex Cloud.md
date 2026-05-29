---
tags: [company/openai, async-agent, autonomous-coding, codex, gpt-5]
created: 2026-05-28
---

# Codex Cloud

OpenAI Codex Cloud is the cloud-async sibling of the Codex CLI — a sandboxed agent that runs many software-engineering tasks in parallel, each in its own VM, network-disabled by default. Launched as a research preview in May 2025, it represents OpenAI's bet that async coding agents become the default consumption pattern for frontier coding models.

## Background

- **Maker:** OpenAI.
- **Original Codex (2021):** The model behind the original GitHub Copilot.
- **Codex (2025 relaunch):** Two surfaces — a terminal CLI (`openai/codex`, open source) and Codex Cloud (web-based async agent).
- **Launch of Codex Cloud:** Research preview, May 2025. Powered by codex-1 (an OpenAI o3 variant post-trained for software engineering).
- **Model evolution:**
  - codex-1 (May 2025) — based on o3.
  - GPT-5-Codex (late 2025).
  - GPT-5.3-Codex (early 2026) — SOTA on SWE-Bench Pro and Terminal-Bench at announcement.

## Funding & Traction

- **Funding:** OpenAI-internal.
- **Distribution:** Bundled into ChatGPT Plus / Pro / Team / Enterprise plans; available via API.
- **Adoption:** OpenAI has not published Codex Cloud-specific task volumes. Anecdotally widely used by OpenAI's own engineering org and by ChatGPT Plus subscribers experimenting with the cloud agent surface.

## Architecture

- **Cloud sandbox per task.** Each task runs in its own isolated VM preloaded with the user's repo. Network disabled by default for safety.
- **Parallel by default.** Designed for fan-out — dispatch many tasks at once, review PRs as they complete.
- **Loop:** Agent reads task, plans, executes code, runs tests, iterates until tests pass or task converges.
- **Surfaces:** Web UI at chatgpt.com/codex (or developers.openai.com/codex/cloud), GitHub integration for PR output, API access.
- **Model backbone:** codex-1 → GPT-5-Codex → GPT-5.3-Codex (current as of early 2026).
- **SWE-bench Verified:**
  - codex-1 at launch (May 2025): ~69.1% (vs. Claude Sonnet 4 at ~72.7% same period). OpenAI initially evaluated on 477 of 500 tasks because 23 didn't run on their infra; later fixed to report all 500.
  - GPT-5.3-Codex: SOTA on SWE-Bench Pro (long-horizon variant) and Terminal-Bench at early-2026 announcement.

## Pricing / Access

- **Included with paid ChatGPT plans** (Plus, Pro, Team, Enterprise) at tier-specific quotas.
- **API:** Pay-per-token via OpenAI's standard model pricing.
- **Codex CLI:** Free, open source (Apache 2.0), runs locally — separate from Codex Cloud.

## Differentiators

- **First-party frontier model.** OpenAI's only competitor with this much model+harness vertical integration is Anthropic (Claude Code). Cognition, Factory, Google, GitHub are all model consumers; OpenAI is making both.
- **Parallel-by-default UX.** Codex Cloud is designed for fan-out across many tasks at once — the harness is multi-agent management, not single-session puppeteering.
- **Network-disabled sandbox.** Strong default-deny posture is a differentiator vs. Devin's full-VM-with-internet model.
- **Open-source CLI sibling.** The `openai/codex` CLI is open source, which is unusual for OpenAI and gives Codex Cloud a credible local-execution counterpart.
- **Benchmark leadership through model upgrades.** Codex Cloud rides every GPT-5.x post-train cycle — its scores improve without harness changes.

## See Also

- [[Autonomous Coding Agents]]
- [[Devin]]
- [[Jules]]
- [[GitHub Copilot Workspace]]
- [[OpenHands]] — open-source equivalent in architecture
- [[Codex CLI]] — the terminal sibling
