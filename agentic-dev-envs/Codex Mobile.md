---
tags: [tool, mobile-coding, openai, codex, ade-adjacent]
created: 2026-05-28
---

# Codex Mobile

Codex Mobile is OpenAI's coding agent inside the ChatGPT mobile app — announced May 14, 2026 at OpenAI's developer event. It is the second-largest mobile surface in this category after GitHub Mobile + Copilot, and it lands on a user base of more than 4 million weekly Codex users. Like Cursor Mobile and Claude Code's Remote Control, it is a remote, not an IDE: tasks run on the user's Mac, files and credentials never leave the machine, and the phone gets the diffs, approvals, and steering interface.

## Origin
- Announced May 14, 2026 — rolled out in preview on iOS and Android, across all ChatGPT plans including Free and Go, in all supported regions.
- Lives inside the ChatGPT mobile app (not a separate Codex app), reflecting OpenAI's product strategy of folding everything into ChatGPT as the single surface.
- Powered by GPT-5.3-Codex as of launch.
- Sits alongside Codex CLI, Codex Cloud, and Codex in the IDE — same backend, mobile-shaped UI.

## Adoption
- Over 4 million weekly Codex users at the time of launch per OpenAI.
- Enterprise customers cited at launch: Virgin Atlantic, Cisco, Notion, Rakuten.
- Codex Labs program with Accenture, Capgemini, PwC for enterprise rollout — mobile is part of that pitch.
- Launch broadly framed by OpenAI as "work with Codex from anywhere" — explicit positioning against laptop-bound competitors.

## Product
- Start tasks from the phone; the task runs against a paired macOS Codex session.
- Monitor active threads, see diffs, approve commands, steer the agent mid-run.
- Push notifications on task completion or blocking events.
- No in-app code editor — cannot directly write or modify code on the device.
- Secure relay between phone and Mac — only diffs, status, and approvals cross the wire; code stays local.
- Roadmap: Windows compatibility (Mac-only at launch).

## Pricing
- Available across all ChatGPT plans (Free, Go, Plus, Pro, Business, Enterprise).
- Usage limits and concurrency vary by plan; no separate Codex Mobile SKU.

## Differentiators
- Distribution — the ChatGPT mobile app is one of the most-installed AI apps in the world, which means Codex Mobile reaches users who would never download Cursor's standalone app.
- Pricing reach — including Free and Go means students, hobbyists, and prosumers can run a real coding agent from their phone for $0, which no one else in this cluster offers at that price.
- The Mac dependency is the same constraint Cursor and Claude Code face — Apple's sandbox rules effectively force the "phone as remote" architecture across all three.
- Free-tier rollout pressures Anthropic and Anysphere — Claude Code's Remote Control and Cursor Mobile both require paid plans to be useful.

## See Also
- [[Mobile Coding Agents]]
- [[Cursor Mobile]]
- [[Claude Code]]
- [[Codex CLI]]
- [[Codex Cloud]]
