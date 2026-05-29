---
tags: [tool, sre, on-call, ai-agent, specialty-agent]
created: 2026-05-28
---

# Sherlocks.ai

Sherlocks.ai is an earlier-stage AI SRE platform with a multi-agent architecture — 16+ specialized agents that fan out to investigate a single incident in parallel. The product deploys inside the customer's VPC with strictly read-only permissions, addressing the trust concerns that block higher-touch tools like [[Resolve.ai]].

## Origin

Founded by Gaurav Toshniwal (CEO) and Akshat Jain (CTO), both ex-CTOs who spent years on on-call rotations before building the product. Early stage; not heavily covered by press yet.

## Funding & Traction

- Funding details not heavily disclosed publicly.
- Self-described as 24x7 SRE teammates.
- Cited claims: 70% less downtime, 90% less alert noise, MTTR hours-to-minutes.

## Product

Sherlocks dispatches 16+ specialized agents on each incident — one for logs, one for metrics, one for config drift, one for similar past incidents, etc. They coordinate and merge findings into one root-cause analysis.

Key design choices:

- **VPC-deployed.** Runs entirely inside the customer's network. Data never leaves.
- **Read-only integrations.** Same trust posture as [[Cleric]].
- **Slack-native.** Monitors incident channels, post-mortems, and team conversations to build contextual understanding.
- **PagerDuty + Datadog integrations.**

## Pricing

Not publicly disclosed.

## Differentiators

- **Multi-agent fan-out architecture.** Conceptually different from single-agent investigators — more parallelism, potentially faster.
- **VPC + read-only by default.** Strongest security posture in the SRE cluster.
- **Slack conversational learning.** Mines historical incident discussions, not just monitoring data.

## Risk factors

- Earliest stage of the three notable AI SRE players. Will have to outpace [[Resolve.ai]] and [[Cleric]] on either price or trust.
- Multi-agent orchestration is complex to operate reliably — and reliability is the entire selling point.
- Less brand awareness; sales motion starts cold.

## See also
- [[Resolve.ai]]
- [[Cleric]]
- [[Charlie Labs]]
- [[Specialty Agents]]
