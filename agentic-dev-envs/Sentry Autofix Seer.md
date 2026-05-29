---
tags: [tool, debugging, observability, ai-agent, specialty-agent]
created: 2026-05-28
---

# Sentry Autofix (Seer)

Sentry is the established observability incumbent that built an AI debugging agent — Seer — on top of its existing telemetry mountain. The bet: nobody has more error context than Sentry already has, so attaching an LLM to that data should produce the most accurate root-cause analyses. Available as a $40/active-contributor add-on, Seer is the most-monetized debugging agent in the cluster by virtue of Sentry's existing distribution.

## Origin

Sentry was founded in 2008 by David Cramer and Chris Jennings, originally as an open-source error tracker. By 2025 it had ~$400M ARR in observability. Seer was launched as Sentry's AI strategy in 2024 and went GA on paid plans in 2025.

## Funding & Traction

- Sentry total raised: ~$217M, last round 2022 at ~$3B valuation.
- ~4M+ developers, 100K+ orgs use Sentry.
- Seer is bundled with Team and Business plans as an add-on.

## Product

Seer is positioned as Sentry's AI debugger. Two key sub-products:

1. **Autofix.** When an issue lands in Sentry, Seer:
   - Analyzes the stack trace, breadcrumbs, span data, profile, logs.
   - Connects to the linked GitHub repo to read the relevant code.
   - Proposes a root cause hypothesis.
   - Generates a fix and opens a PR.

2. **Issue triage.** Auto-categorizes incoming errors and prioritizes by likely user impact.

Seer's edge is **context Sentry already has** — the same telemetry the developer would look at manually, plus the code, plus the deploy history.

## Pricing

- $40/month per "active contributor" (a user who opens 2+ PRs/month against a Seer-enabled repo).
- Billed on top of standard Sentry subscription (Team or Business).
- Not part of the pay-as-you-go event budget.

## Differentiators

- **Built-in telemetry context.** No other debugging agent starts with Sentry's level of production context.
- **Distribution to ~100K orgs.** Sentry can flip Seer on for its existing base without acquisition cost.
- **Pricing aligned with use.** Charging per contributor (not per seat) ties cost to actual benefit.

## Risk factors

- Tied to Sentry. Customers not on Sentry (using Datadog, Honeycomb, etc.) don't enter the funnel. Datadog and others will ship their own equivalents.
- Pricing-per-contributor introduces shadow billing surprises ("who counts as active?").
- [[Charlie Labs]] and [[Resolve.ai]] approach debugging without requiring lock-in to one observability vendor.

## See also
- [[Charlie Labs]]
- [[Resolve.ai]]
- [[Cleric]]
- [[Specialty Agents]]
