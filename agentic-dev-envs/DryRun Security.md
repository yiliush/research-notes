---
tags: [tool, security, sast, ai-agent, specialty-agent]
created: 2026-05-28
---

# DryRun Security

DryRun Security is the Austin-based AI-native SAST entry — a 2023 founding that raised $8.7M seed in January 2025 to build "Natural Language Code Policies." The pitch is that legacy SAST tools require teams to maintain hundreds of scripted rules; DryRun lets AppSec teams write policies in plain English and have an LLM enforce them in code review.

## Origin

Founded in 2023 by Ken Johnson and James Wickett, both AppSec veterans with deep DevSecOps backgrounds (Wickett is widely known in the chaos engineering and DevSecOps communities). Austin headquarters.

## Funding & Traction

- Seed (Jan 2025): $8.7M led by LiveOak Ventures and Work-Bench with Cannage Capital.
- Cited usage: 250,000+ code reviews per month run through DryRun — higher than other AI-native SAST competitors per their own marketing.

## Product

DryRun Security's core capability is **Contextual Security Analysis** — analyzing PRs not just for known vulnerability patterns but for "did this change introduce something that violates our policy?"

Key features:

- **Natural Language Code Policies (NLCP).** Write security policies as English sentences; the agent enforces them on every PR.
- **PR-native.** Sits in the GitHub PR flow rather than a separate dashboard.
- **AI agents specialized by domain.** Auth agent, secrets agent, IDOR agent, etc.

## Pricing

Sales-led; not publicly disclosed.

## Differentiators

- **Natural-language policy authoring.** Major UX advance vs. Semgrep rules or CodeQL queries.
- **PR-native delivery.** Meets developers where they work.
- **AppSec founder credibility.** Wickett's DevSecOps brand gives them sales lead pipeline.

## Risk factors

- [[Snyk]] and [[Endor Labs]] are vastly better-funded and can add NLCP features quickly.
- Small seed round limits go-to-market velocity.
- "AI-native SAST" is a crowded narrative; differentiation requires sustained marketing and proof of accuracy.

## See also
- [[Snyk]]
- [[Endor Labs]]
- [[Apiiro]]
- [[CodeRabbit]]
- [[Specialty Agents]]
