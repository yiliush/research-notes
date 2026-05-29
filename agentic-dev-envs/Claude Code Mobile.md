---
tags: [tool, mobile-coding, anthropic, claude-code, ade-adjacent]
created: 2026-05-28
---

# Claude Code Mobile

Claude Code's mobile surface is the official Anthropic story for running a coding agent from a phone. Two layered capabilities matter: Claude Code became available inside the Claude iOS app in October 2025, and the dedicated Remote Control feature shipped February 25, 2026 — a `/rc` (or `claude remote-control`) command that prints a QR code, you scan it in the Claude mobile app, and your phone now drives the same Claude Code session as your laptop. The Android Claude app followed in March 2026, making Anthropic the first major coding-agent vendor with parity across iOS, Android, and web.

## Origin
- Claude Code (the CLI) launched February 2025.
- Claude iOS app added Claude Code surface in October 2025.
- Claude Android app launched March 2026.
- Remote Control shipped February 25, 2026 — explicitly to formalize the QR-pairing workflow that third-party apps like Happy, Nimbalyst, and Vicoa had been doing.
- Apple's Xcode 26.3 (April 2026) integrated the Claude Agent SDK directly into Xcode, which is the closest thing to a first-party on-device coding-agent runtime on iOS.

## Adoption
- Claude Code passed a $2.5B annualized run rate by February 2026 — more than doubled since the start of the year.
- Mobile usage not separately disclosed, but the third-party ecosystem (Happy, Nimbalyst, Vicoa, Vibe Code Anywhere) ahead of the official feature is itself evidence of meaningful demand.
- Xcode integration brings Claude Code into the default macOS developer toolchain, which extends the iPhone story via TestFlight-style flows.

## Product
- Claude iOS/Android app — chat with Claude, including Claude Code-style tool use.
- Remote Control — pair a running Claude Code session (laptop) with the Claude mobile app via QR; phone now sends prompts, sees diffs, approves tool calls, with the same files, MCP servers, and project context as the desktop.
- End-to-end encrypted relay between desktop and phone.
- Third-party ecosystem (still relevant): Happy (OSS), Nimbalyst (kanban-style UI), Vibe Code Anywhere — all built on Claude Code's hooks.
- Xcode 26.3 — Claude Agent SDK exposed directly in Apple's IDE, the first major IDE-level integration on a hyperscaler-owned platform.

## Pricing
- Free with a Claude account; Claude Code usage runs on the paired session, which requires a Claude Pro, Max, Team, or Enterprise plan.
- Remote Control adds no cost beyond the underlying Claude Code session.

## Differentiators
- Cross-platform parity earliest — Anthropic shipped both iOS and Android well ahead of Cursor's Android plans.
- Apple partnership — Xcode 26.3 integration is the only deep platform integration any agent has secured with a hyperscaler-owned IDE.
- Remote Control is the cleanest QR-pairing flow in the cluster — five seconds to set up.
- The same architectural constraint as Cursor Mobile and Codex Mobile: the phone is a remote, not a runtime. Real execution still happens on the paired computer.

## See Also
- [[Mobile Coding Agents]]
- [[Claude Code]]
- [[Cursor Mobile]]
- [[Codex Mobile]]
