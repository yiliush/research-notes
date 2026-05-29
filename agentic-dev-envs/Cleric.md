---
tags: [tool, sre, on-call, ai-agent, specialty-agent]
created: 2026-05-28
---

# Cleric

Cleric is one of the earliest AI SRE startups, positioning itself as "the first self-learning AI SRE." Where [[Resolve.ai]] competes on founder pedigree and capital, Cleric competes on the framing of operational memory — every incident the agent investigates becomes context for future ones, building organization-specific runbook knowledge.

## Origin

Founded ~2023, backed by Vertex Ventures US and Zetta Venture Partners. Founders Willem Pienaar (ex-Tecton, creator of Feast feature store) and others — strong ML infrastructure background.

## Funding & Traction

- Total raised: $9.8M.
- Vertex Ventures US led a $5.5M seed; Zetta also participated.
- Named Gartner Cool Vendor 2025 in AI for SRE and Observability.

## Product

Cleric is an AI agent that lives in your PagerDuty/Slack rotation and:

1. **Investigates alerts autonomously** — pulls signals from observability tools, correlates them, runs analysis.
2. **Produces root-cause hypotheses** with citations to the underlying data.
3. **Learns from outcomes.** Operational memory layer captures what was tried, what worked, and surfaces that next time.
4. **Read-only by default.** Suggests remediations rather than executes — a conservative trust posture.

## Pricing

Sales-led; not publicly disclosed.

## Differentiators

- **Operational memory framing.** Self-learning loop differentiates from one-shot investigators.
- **Read-only posture.** Less risk than agents that auto-remediate; appeals to enterprises burned by automation gone wrong.
- **Gartner Cool Vendor recognition.** Useful for enterprise procurement signaling.

## Risk factors

- Significantly less funded than [[Resolve.ai]] ($9.8M vs $200M+) — operates in the shadow of a much larger competitor.
- "Self-learning" is a marketing differentiator competitors can copy.
- Read-only posture is conservative — buyers may eventually demand auto-remediation, which Resolve.ai is more aggressive about.

## See also
- [[Resolve.ai]]
- [[Sherlocks.ai]]
- [[Sentry Autofix Seer]]
- [[Specialty Agents]]
