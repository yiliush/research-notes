---
tags: [tool, debugging, ai-agent, daemon, specialty-agent]
created: 2026-05-28
---

# Charlie Labs

Charlie Labs is the rare ADE specialist betting on **always-on daemons** as the unit of automation, defined declaratively in markdown files. Charlie acts as an autonomous TypeScript engineer across GitHub, Linear, and Slack — fixing bugs, monitoring CI, and creating PRs from Linear tickets, all without explicit prompting.

## Origin

Founded ~2024, San Francisco. Team includes ex-OpenAI / dev tools engineers (specific founder names less prominent than other specialists). Charlie joined Linear's Agents partner program as one of the launch agents in 2025.

## Funding & Traction

- $10M seed round.
- SOC 2 Type II attestation (without exception).
- Integrates with Linear, GitHub, Slack, Datadog.
- Runs on GPT-5 as of late 2025.

## Product

The interesting design choice: Charlie's automations are **Daemons** defined in `.md` files in your repo. You write something like:

```
# CI Babysitter Daemon
When CI fails on main, investigate the failure, find the root cause,
and either propose a fix as a PR or post a Slack message tagging the relevant engineer.
```

Charlie's runtime reads these, executes them 24/7 across the integrations.

Capabilities:

- **Debugging.** Read-only prod DB access + Datadog integration to investigate live issues.
- **Linear-to-PR.** Take a Linear ticket, build the feature with E2E tests, open a PR.
- **CI watchdog.** Auto-investigate and fix CI failures.
- **PR review.** Lightweight TypeScript-focused PR review.

## Pricing

Sales-led; not publicly disclosed.

## Differentiators

- **Declarative markdown automations.** Aligns with the agent-native ethos — automations live in the repo, reviewable in PRs, version-controlled.
- **TypeScript depth.** Picked one language well rather than chasing every ecosystem.
- **Linear Agents integration.** First-class partner with the issue tracker many AI-forward teams use.
- **Read-only prod DB access.** Most debugging agents don't have this — it dramatically improves root-cause analysis.

## Risk factors

- Daemons-from-md is a novel UX that may not generalize. Engineers might prefer explicit triggers.
- Competes against horizontal agents ([[Claude Code]], Cursor) plus specialized SRE tools ([[Resolve.ai]], [[Cleric]]).
- TypeScript-only focus limits TAM.
- Small relative to category leaders — $10M seed implies need for clear product-market fit before larger raise.

## See also
- [[Sentry Autofix Seer]]
- [[Resolve.ai]]
- [[Cleric]]
- [[Specialty Agents]]
