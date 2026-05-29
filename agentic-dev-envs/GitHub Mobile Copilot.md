---
tags: [tool, mobile-coding, github, copilot, ade-adjacent]
created: 2026-05-28
---

# GitHub Mobile + Copilot

GitHub Mobile is the longest-running developer mobile app in the cluster, and through 2025–2026 it became the default mobile surface for Copilot's cloud coding agent. Copilot Chat lives inside GitHub Mobile, the Copilot coding agent can be started and steered from there, and the April 2026 update extended cloud-agent workflows beyond PRs to include codebase research, implementation-plan generation, and branch-level edits — all from a phone.

## Origin
- GitHub Mobile launched 2019 (iOS) and 2020 (Android).
- Copilot Chat integration arrived in 2024 as Copilot expanded from inline completion into a chat surface.
- February 2026 update: Copilot Pro and Pro+ users can pick a model when starting a coding-agent session from mobile.
- April 8, 2026 update: cloud-agent workflows extended past pull-request creation to include research, planning, and branch-level edits without immediately opening a PR.

## Adoption
- GitHub Mobile is installed on tens of millions of devices; Copilot has 20M+ paying users by 2026 reporting.
- No standalone mobile Copilot revenue, but the bundled distribution is the largest in this sub-cluster.
- Copilot Chat is free on mobile and CLI with 2,000 completions and 50 chat messages per month, broadening the mobile entry funnel.

## Product
- Copilot Chat in GitHub Mobile — ask questions about repos, issues, PRs, code, with optional public-code and Bing search.
- Copilot coding agent — start a cloud agent on a repo from mobile; pick a model (Pro/Pro+); the agent runs in GitHub-hosted infrastructure, reports back in the app.
- Research mode (April 2026) — ask the agent to investigate the codebase and produce a structured report.
- Implementation plan mode — agent drafts a plan before writing code, user reviews on phone, agent then executes on a branch.
- Branch edits without auto-PR — review the diff, iterate, only open the PR when ready.
- Org knowledge (Copilot Enterprise) — agent can search internal docs and repos as context.

## Pricing
- Free Copilot tier: 2,000 completions + 50 chat messages/month.
- Pro: $10/month — full Copilot, model picker in mobile.
- Pro+: $39/month.
- Business: $19/user/month.
- Enterprise: $39/user/month — includes org knowledge in mobile.

## Differentiators
- Distribution moat — GitHub Mobile is already on the developer's phone; no separate install required.
- Cloud-execution model — unlike Cursor/Codex/Claude Code's "phone as remote for desktop session," GitHub's coding agent runs in GitHub's cloud, so no Mac dependency. The phone is a thin client to a fully cloud-side agent.
- The only mobile coding-agent surface that is materially useful without a paired laptop.
- Tightly bound to the PR-as-unit-of-work mental model — fine for code review and async tasks, weaker for exploratory work where Codex/Cursor/Claude have richer UI.

## See Also
- [[Mobile Coding Agents]]
- [[GitHub Copilot]]
- [[Codex Mobile]]
- [[Cursor Mobile]]
