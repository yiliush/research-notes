---
tags: [tool, sre, on-call, ai-agent, unicorn, specialty-agent]
created: 2026-05-28
---

# Resolve.ai

Resolve.ai is the breakout AI SRE startup — the first to hit unicorn valuation in this slice of the cluster. The company autonomously participates in on-call rotations, investigating incidents, running root-cause analyses, and either suggesting or executing remediations. Founded by the ex-Splunk observability leadership team, it positions itself as an "AI Production Engineer" sitting next to humans.

## Origin

Founded by Mayank Agarwal (CTO) and Spiros Xanthos (CEO), both with 20+ years operating production systems at scale. Both were senior leaders at Splunk's observability business, and Xanthos co-created OpenTelemetry. The founding team's CV is one of the most credentialed in the cluster.

## Funding & Traction

- Total raised: $200M+.
- Seed (Oct 2024): $35M led by Greylock. Backers include Fei-Fei Li (World Labs), Jeff Dean (Google DeepMind).
- Series A (Feb 2026): $125M at $1B valuation, led by Lightspeed Venture Partners with Greylock, Unusual Ventures, Artisanal, A*, DST Global.
- Resolve AI Labs spinout: $40M at $1.5B valuation.
- Customer outcomes cited: 70%+ reduction in incident resolution time, 75% on-call productivity boost, 20 hours/week saved per engineer.

## Product

Resolve.ai's AI Production Engineer:

1. **On-call rotation participation.** Pages itself first; engineers escalate to it.
2. **Autonomous investigation.** Pulls logs, traces, metrics, configs across the stack to form a hypothesis.
3. **Root-cause analysis.** Posts a structured analysis with evidence into the incident channel.
4. **Remediation.** Suggests or (with permission) executes runbook actions.
5. **Memory across incidents.** Learns from past incidents to recognize recurring patterns.

## Pricing

Enterprise, not publicly disclosed. Likely six- to seven-figure annual ACVs based on customer profile and unicorn valuation math.

## Differentiators

- **Founder credibility.** Splunk observability + OpenTelemetry co-creator. SRE buyers trust this team to handle production correctly.
- **Multi-tool stack coverage.** Datadog, Splunk, NewRelic, PagerDuty, Slack, Kubernetes — works across whatever the customer already has.
- **Unicorn-level capital.** $200M+ funded means Resolve can outhire and outsell the rest of the SRE cluster combined.

## Risk factors

- Production access is the highest-trust capability in this entire cluster. One bad auto-remediation could be catastrophic.
- Datadog, PagerDuty, Splunk will all ship "AI SRE" features themselves.
- Sky-high valuation requires sustained 5x+ growth to justify; unclear whether SRE budgets can absorb it.

## Notable customers

Specific names not widely disclosed but customer outcome figures suggest enterprise-tier deployments.

## See also
- [[Cleric]]
- [[Sherlocks.ai]]
- [[Charlie Labs]]
- [[Sentry Autofix Seer]]
- [[Specialty Agents]]
