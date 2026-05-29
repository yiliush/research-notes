---
tags: [tool, open-source, ai-ide, cursor-alternative, archived, ade-cluster]
created: 2026-05-28
---

# Aide

Aide (codestoryai/aide) was the first credible open-source Cursor alternative — a VS Code fork from London-based [[CodeStory]] that shipped its own agent harness (Sidecar) and posted competitive SWE-bench-lite scores before [[Void]] or [[Pear AI]] existed. Archived February 2025 when CodeStory pivoted upstream to focus on the agent layer rather than the editor wrapper. The codebase remains read-only on GitHub at ~2.2k stars, a usable artifact for anyone wanting to fork their own AI-native IDE.

## Origin
- Built by CodeStory (Sandeep Mistry, Naresh Kumar; YC S22 batch). London-based.
- VS Code fork started ~late 2023; public release 2024.
- Positioned originally as "an AI-native, privacy-first IDE." Privacy story: everything (including chat history) stored in a local SQLite DB; no telemetry to CodeStory servers.
- Powered by CodeStory's own agent harness called Sidecar — a Rust-based binary that handled tool use, planning, and the SWE-bench loop.

## Adoption
- GitHub stars verified May 2026: ~2.2k. Modest.
- Archive announcement: February 25, 2025. The repo is read-only.
- Listed installs and active user counts never published.
- Real impact was indirect — Aide's existence proved an OSS VS Code fork with a serious agent was viable, which set up the playbook [[Void]] and [[Pear AI]] later executed.

## Architecture
- VS Code fork (95.5% TypeScript).
- Sidecar agent harness (Rust) — separate binary, communicated with the editor via local IPC.
- Combined chat + edit UI: brainstorm in chat, jump into multi-file edit.
- "Proactive agent" — watched linter output and self-prompted to fix issues without explicit user request. Unusual at the time.
- Spotlight-style inline editing widget (Cmd-K).
- License: AGPL-3.0 (deliberately copyleft to discourage closed forks).

## Pricing
- Free, OSS. CodeStory monetized via [[CodeStory]]'s hosted services, not the editor.

## Differentiators (at time of archive)
- Posted competitive SWE-bench-lite scores when most OSS IDEs had nothing.
- Sidecar as a separable agent runtime — design that anticipated where the category went (separating the agent harness from the editor shell).
- AGPL-3.0 license is the strictest in this corner of the ecosystem.
- "First mover among credible OSS Cursor alternatives" — Aide predates Void by ~6 months.

## Why It Was Archived
- CodeStory's bet shifted: maintaining a VS Code fork is enormous engineering effort and the editor wrapper is the least defensible layer in the stack. The team chose to focus engineering on Sidecar and the agent layer.
- See [[CodeStory]] for the company's current direction.

## Aftermath
- AGPL license + archived repo invites forks. Several have appeared but none have meaningful traction.
- The architectural template (editor + separate agent binary) is now common — [[Claude Code]], [[Codex CLI]], and [[Gemini CLI]] all run as separate binaries that any editor can integrate.

## See Also
- [[CodeStory]] — parent company; still active
- [[Void]] — successor in the "OSS Cursor fork" niche
- [[Cursor]]
- [[Continue]]
- [[Pear AI]]
- [[SWE-bench and Coding Benchmarks]]
- [[Agent Harness]]
- [[Green Shoots]]
