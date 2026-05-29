---
tags: [company/google, async-agent, autonomous-coding, jules, gemini]
created: 2026-05-28
---

# Jules

Jules is Google Labs' autonomous coding agent — Google's answer to Devin and the GitHub Copilot agent. It clones your repo into a Google Cloud VM, runs Gemini-powered work asynchronously, and returns a pull request. Bundled into Google AI Pro/Ultra plans, it's the first hyperscaler-distributed async agent.

## Background

- **Maker:** Google Labs, with model backbone from Google DeepMind (Gemini family).
- **Timeline:**
  - **December 2024:** Private preview inside Google Labs.
  - **May 20, 2025:** Public beta announced at Google I/O.
  - **August 6, 2025:** Generally available worldwide with paid plans.
  - **October 2, 2025:** Jules Tools (CLI) and Jules API launched, turning Jules from a closed web UI into a composable component for external pipelines.

## Funding & Traction

- **Funding:** Google-internal; no separate raise. Effectively unlimited capital.
- **Distribution leverage:** Bundled into existing Google AI subscription plans, which reach hundreds of millions of consumer Gemini users — by far the broadest distribution surface in this cluster.
- **Adoption numbers:** Google has not published Jules-specific MAU or task counts as of mid-2026. TechCrunch (October 2025) framed Jules as "competition heating up" rather than a clear leader.

## Architecture

- **Cloud sandbox:** Each task clones the repo into a Google Cloud VM. Network-isolated by default.
- **Async loop:** Receives a task (issue, prompt, or CLI command), produces a plan, executes, runs tests, opens a PR with a diff and reasoning summary. Optional audio changelog narration.
- **Surfaces:** Web UI at jules.google, GitHub integration, Jules CLI (`jules`), Jules API.
- **Model backbone:** Gemini (specific variant not publicly pinned; presumably Gemini 2.5 Pro / 3.0 by mid-2026).
- **SWE-bench:** Google has not published a clean Jules SWE-bench Verified number. Gemini 2.5 Pro alone (without Jules' scaffolding) scored in the high-60s/low-70s in 2025 disclosures.

## Pricing / Access

- **Free tier:** Up to 15 daily tasks, 3 concurrent.
- **Google AI Pro:** $19.99/month — ~5x the free limits.
- **Google AI Ultra:** $124.99/month — ~20x the free limits.
- **API:** Programmatic access via Jules API (October 2025+); pricing on metered task quotas.

## Differentiators

- **Distribution.** Bundled into Google AI Pro/Ultra means Jules ships to existing Gemini subscribers at zero acquisition cost. Nothing else in this cluster has that.
- **Free tier with real headroom.** 15 tasks/day at the free tier is generous compared to Devin (paid only) and Factory (enterprise only).
- **Jules Tools (CLI) + API.** Decoupled from the web UI in October 2025 — Jules is one of the few agents in this cluster usable from terminal pipelines and CI.
- **Audio changelogs.** Niche but distinctive — Jules narrates what it did.
- **No flashy benchmark claims.** Google has been conservative on SWE-bench marketing for Jules, which is either humility or a signal it's not leading.

## See Also

- [[Autonomous Coding Agents]]
- [[Devin]]
- [[GitHub Copilot Workspace]]
- [[Codex Cloud]]
- [[Gemini]]
