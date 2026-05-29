---
tags: [tool, mobile-coding, cursor, ade-adjacent, ai-ide]
created: 2026-05-28
---

# Cursor Mobile

Cursor Mobile is Anysphere's iOS app for monitoring and steering Cursor agents from a phone. It is not an IDE on your phone — it is a remote control for the agents running on your devbox or in Cursor's cloud Background Agents. Launched in 2025 (preceded by the web app at cursor.com/agents in June 2025), it formalized a workflow that power users had been hacking together with SSH and tmux: kick off a long-running task on the laptop, walk away, approve, redirect, or kill it from the phone.

## Origin
- Built by Anysphere (Cursor) — the iOS app shipped after the web app for managing Cursor Background Agents launched June 30, 2025.
- iOS-first; no native Android app as of April 2026. Android users get a fully functional PWA at cursor.com/agents.
- Tied to Cursor's Background Agents architecture from Cursor 2.0 (October 2025), which made parallel cloud-running agents a first-class concept.

## Adoption
- Distributed via the App Store; available to all Cursor Pro and higher subscribers.
- No standalone adoption numbers; usage is gated by having an active Background Agents workload.
- Most useful for the Cursor Ultra / Enterprise customer profile running multiple parallel agents on long-horizon tasks.

## Product
- Send prompts to a devbox or to a Background Agent; results stream back to the phone.
- Approve / reject agent commands when the agent needs a human in the loop.
- Review diffs and agent outputs on a mobile-friendly UI.
- Model picker — choose Claude Opus 4.6, Claude Sonnet 4.6, GPT-5.4, or Gemini 3.1 Pro per request.
- Push notifications when an agent is blocked or finishes a task.
- Not a mobile editor — you cannot meaningfully write or edit code in-app. The expected workflow is "agent does the work, you supervise from your phone."

## Pricing
- Free with a Cursor account; requires a paid Cursor plan to do anything substantive (Pro, Pro+, Ultra, Teams, Enterprise).
- No separate mobile SKU.

## Differentiators
- First-class iOS app from the AI-IDE category leader — neither Windsurf nor Zed has shipped a comparable mobile surface.
- Tight integration with Cursor 2.0's multi-agent architecture — the phone is the natural orchestrator for parallel cloud agents.
- Remote-control framing — Cursor leaned into "supervise from the couch" rather than the half-credible "code on your phone" pitch.
- Constrained by Apple's App Store policies — no on-device code execution, which limits how far an Agentic IDE on iOS can really go.

## See Also
- [[Mobile Coding Agents]]
- [[Codex Mobile]]
- [[Claude Code]]
- [[Cursor]]
- [[Replit Agent]]
