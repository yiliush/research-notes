---
tags: [tool, open-source, cli-agent, scrappy, ade-cluster]
created: 2026-05-28
---

# Plandex

Plandex is an open-source, terminal-based AI coding agent built in Go, designed for long-context planning across large projects. It carved out a niche before Claude Code and Codex CLI existed by treating "the plan" as a first-class artifact — a sandboxed, reviewable, branchable workspace separate from your files. By May 2026 it has crossed 15k GitHub stars but the hosted Plandex Cloud is winding down, leaving the project in self-hosted maintenance mode.

## Origin
- Created by Dane Schneider (sole founder), public launch March 2024 from a beta that started late 2023.
- Solo-founder, bootstrapped project. No VC funding disclosed.
- Written in Go (93%+ of codebase) — unusual in a category dominated by Python and TypeScript agents.
- Roadmap explicitly positioned Plandex against Aider (which was the only other serious terminal agent at the time).

## Adoption
- GitHub stars verified May 2026: ~15.4k (plandex-ai/plandex).
- 30+ programming languages supported via tree-sitter.
- Linux Foundation: no affiliation — the user's premise conflated Plandex with [[Goose]] (Block donated Goose to the Linux Foundation in 2025).
- Last release: cli/v2.2.1 in July 2025. No commits since October 2025.
- Plandex Cloud wind-down announced Oct 3, 2025; no new cloud signups, existing users grandfathered. Self-hosted mode unaffected.

## Architecture
- CLI-only — no editor integration, no IDE plugin.
- Multi-model: routes across Anthropic, OpenAI, Google, and open-source providers via configurable model packs. Each role (planner, builder, summarizer, verifier) can use a different model.
- Context handling: up to 2M tokens of direct context; ~20M+ token projects supported via tree-sitter project maps.
- "Cumulative diff sandbox": all proposed edits land in a separate workspace branch and are reviewed before being applied to user files. This is the signature feature.
- Git-style branching for plans: fork a plan, try multiple approaches, merge the winner.
- Auto-debug loop for terminal command failures.
- License: MIT.

## Pricing
- Self-hosted: free, MIT-licensed.
- Plandex Cloud: previously $20/month Pro, now winding down. No new subscriptions as of Oct 2025.

## Differentiators
- "Plans as branchable artifacts" — closer to a git workflow than a chat session. No other agent treats plans this way.
- Massive context handling via project maps was state-of-the-art when shipped; now table stakes for [[Claude Code]] and [[Codex CLI]].
- Go binary distribution = trivial install on servers and CI without Python/Node deps.
- Founder bandwidth limit is visible — single-maintainer project competing against teams at Anthropic and OpenAI is the proximate cause of the cloud wind-down.

## See Also
- [[Aider]] — the closest competitor and precursor
- [[Claude Code]] — the platform agent that ate Plandex's air
- [[Codex CLI]] — same dynamic
- [[CLI Coding Agents]] — cluster index
- [[Green Shoots]]
