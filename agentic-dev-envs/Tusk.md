---
tags: [tool, testing, ai-agent, specialty-agent]
created: 2026-05-28
---

# Tusk

Tusk (usetusk.ai) is a Y Combinator W24 testing agent with a distinctive technical approach: it records real production traffic, then replays those traces against new code to generate realistic unit and API tests. The result is high-coverage test suites grounded in actual user behavior rather than synthetic happy-path scenarios.

## Origin

Founded in 2023 by Marcel Tan and Sohail Kshirsagar. The founders had previously built one of the first publicly available AI coding agents and noticed regressions were the dominant pain point — not initial code generation. Tusk took shape during YC W24.

## Funding & Traction

- Total raised: $2.1M across two rounds.
- AWS Activate participant, with AWS credits and go-to-market support.
- Customers cited: DeepLearning.AI, Wyndly, Afterword.

## Product

Tusk's approach:

1. **Trace recording.** Instrument production to record real user interactions, API calls, DB queries.
2. **Test synthesis.** AI agent converts recorded traces into deterministic unit/integration tests.
3. **Replay on code changes.** New PRs are tested against the trace library to catch regressions before merge.
4. **Coverage agent.** Identifies untested code paths and proposes new tests.

Recently expanded to a more general "AI coding agent that completes your chores" framing covering bug fixes and small feature implementations alongside test generation.

## Pricing

- Free tier and paid plans; specific tiers not heavily published.
- Sales-led for enterprise.

## Differentiators

- **Production-traffic-as-test-source.** Most test generators hallucinate inputs; Tusk uses real ones. This dramatically reduces false-positive test flakes.
- **Regression-first framing.** Sells against the pain of "AI wrote code, now what broke."
- **AWS partnership.** Provides infra discounts and enterprise distribution.

## Risk factors

- Small funding round limits ability to compete with [[QA Wolf]] or [[Momentic]] on go-to-market.
- Production instrumentation requires customer trust and onboarding — long sales cycles for small contract sizes.
- Scope creep into general coding agent territory ([[Charlie Labs]] and horizontal players will dominate that lane).

## See also
- [[QA Wolf]]
- [[Momentic]]
- [[Antithesis]]
- [[Specialty Agents]]
