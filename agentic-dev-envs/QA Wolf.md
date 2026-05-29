---
tags: [tool, testing, managed-service, specialty-agent]
created: 2026-05-28
---

# QA Wolf

QA Wolf is the managed-service play in the AI testing space. Rather than selling tools, it sells a hard outcome: 80% E2E test coverage in four months, unlimited runs, 24-hour failure investigation, fixed monthly fee. The model has scaled to ~$15-20M ARR with ~130 enterprise customers paying $100K-$200K each.

## Origin

Founded in 2019 by Jon Perl and Laura Cressman. Pre-dates the generative AI wave — QA Wolf started as a managed QA service using human QA engineers. AI is now woven through the test authoring and triage process, but the service framing has been consistent from day one.

## Funding & Traction

- Total raised: ~$76M.
- Series A (Sept 2022): $20M led by Inspired Capital.
- Series B (July 2024): $36M led by Scale Venture Partners with Threshold, Inspired, Notation, Ventureforgood.
- ARR: ~$15-20M in 2024 per Sacra.
- Customer base: ~130 companies with ACVs $100K-$200K.

## Product

QA Wolf does not sell software. It sells a contract:

1. Customer onboards their app.
2. QA Wolf engineers + AI agents write E2E tests in Playwright.
3. Service guarantees 80% coverage within 4 months.
4. Unlimited parallel test runs included.
5. Failed tests are triaged by QA Wolf within 24 hours — you get a real bug report, not a flaky-test alert.

Recently added mobile (iOS, Android) test automation to the product.

## Pricing

- Fixed monthly fee, not seat-based. Approximately $4K-$15K/month depending on coverage scope.
- Outcome contract — pricing model is unusual for the category.

## Differentiators

- **Outcome-based pricing.** "We guarantee 80% coverage" is a contractual outcome few competitors offer.
- **Managed triage.** Buyer doesn't see flaky tests — QA Wolf eats the operational pain.
- **Unlimited runs.** Solves the "every PR runs all tests in CI" cost spiral.

## Notable customers

130+ companies; specific logos include Salesloft, HubSpot, Drata.

## Risk factors

- Pure managed-service margins are thinner than pure SaaS. Scale-up requires hiring or aggressively replacing humans with agents.
- [[Momentic]] and [[Tusk]] are unbundling the service into self-serve agent products.
- Outcome guarantees create operational risk if AI agents regress.

## See also
- [[Tusk]]
- [[Momentic]]
- [[Antithesis]]
- [[Specialty Agents]]
