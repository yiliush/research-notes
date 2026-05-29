---
tags: [tool, open-source, cli-agent, github-bot, scrappy, ade-cluster]
created: 2026-05-28
---

# Mentat

Mentat is the AbanteAI project that pioneered the "tag the bot in a PR and let it ship code" pattern. It started in 2023 as an open-source Aider-style terminal coding agent (biobootloader/mentat) and pivoted in 2024 to a closed-source GitHub-native bot (mentat.ai / MentatBot). The original CLI was archived January 2025. The pivot worked: MentatBot scored 38% on SWE-bench Lite (state-of-the-art at the time) and now competes head-on with Cosine's Genie, Sweep, and Diamond by Graphite.

## Origin
- Original Mentat: created by Jakob Köhler ("biobootloader") with co-founder, open-sourced mid-2023 as a terminal coding assistant — direct contemporary of [[Aider]] (Paul Gauthier shipped Aider weeks later).
- Incorporated as AbanteAI. Raised seed funding (~$2M, mostly undisclosed angels per Crunchbase; details thin).
- Pivot: roughly Q2 2024. The team rebranded around the GitHub bot and stopped meaningful work on the CLI. Repo renamed to `archive-old-cli-mentat`, formally archived January 7, 2025.

## Adoption
- Original CLI repo: 2.6k stars at archive (verified May 2026).
- MentatBot: thousands of installs on GitHub Marketplace. Specific install count not published.
- SWE-bench Lite: 38% — was SOTA on date of publish; surpassed in 2025 by Cognition's Devin, Cosine's Genie, and others.

## Architecture
- MentatBot runs as a GitHub App. Users tag `@MentatBot` in issues, PRs, or comments and the agent acts.
- Capabilities: opens PRs to fix issues, reviews PRs, suggests improvements, completes PRs autonomously, fixes CI failures, resolves merge conflicts.
- "Fleet mode": run multiple Mentat agents in parallel across many repos. Positioned as a scaling story for engineering orgs.
- Model layer is proprietary; uses frontier providers under the hood (specific routing not disclosed).
- Web dashboard for managing fleets.

## Pricing
- Free: 10 commits + 50 reviews per month.
- Pro: paid tier with higher limits. Public pricing thin.
- Enterprise: custom.

## Differentiators
- One of the earliest "GitHub-bot as primary interface" agents — predates [[Sweep]]'s pivot and [[Diamond by Graphite]].
- Fleet management as a first-class feature (most competitors still expect one-bot-per-repo workflows).
- The biobootloader brand carries weight in the indie-AI-agent community — he was also creator of the viral "wolverine" (self-healing Python) demo.

## Strategic Position
- Crowded category: GitHub-bot coders now include [[Sweep]], [[Sentry Autofix Seer]], [[Diamond by Graphite]], [[Ellipsis]], [[Tusk]], [[Qodo Merge]], [[CodeRabbit]]. Mentat's edge is fleet semantics and early SWE-bench credibility, but no unique technical moat.
- The CLI archive is a tell: the team concluded terminal-agent volume was being eaten by [[Claude Code]] and [[Codex CLI]]. Smart pivot, but it puts them in a different fight.

## See Also
- [[Aider]] — direct contemporary
- [[Charlie Labs]] — adjacent ("AI engineer" framing)
- [[Sweep]] — closest GitHub-bot competitor
- [[Diamond by Graphite]]
- [[SWE-bench and Coding Benchmarks]]
- [[Green Shoots]]
