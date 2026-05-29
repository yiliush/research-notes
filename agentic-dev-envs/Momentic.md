---
tags: [tool, testing, ai-agent, specialty-agent]
created: 2026-05-28
---

# Momentic

Momentic is the natural-language E2E testing specialist — write tests in plain English ("click the login button, expect to see the dashboard"), let the agent figure out the selectors and adapt as the UI changes. The company crossed 200M+ test steps executed and 390K+ bugs caught in a single month at Series A close.

## Origin

Founded in 2024 by Wei-Wei Wu (CEO), YC W24 alumnus. Earlier engineering experience at fintech and developer tools companies.

## Funding & Traction

- Total raised: ~$19.2M.
- Pre-seed (April 2024): ~$500K from YC.
- Seed (March 2025): $3.7M.
- Series A (Nov 2025): $15M led by Standard Capital with Dropbox Ventures, YC, FCVC, Transpose Platform, Karman Ventures.
- Reported usage: 200M+ test steps and 390K+ bugs caught in last month at Series A.

## Product

Momentic offers a low-code/AI E2E testing platform:

1. **Natural-language test authoring.** "Log in as alice@test.com and add an item to cart." The agent maps that to browser actions.
2. **Self-healing tests.** When the UI changes, the agent updates selectors automatically — eliminates the single biggest flake source in Playwright/Cypress.
3. **Visual + DOM + semantic understanding.** Agent reasons about screenshots and the DOM together.
4. **Web and mobile coverage.**
5. **Verification layer.** Marketing pitch is "AI-era source of truth for software quality" — positioning testing as the gating function for AI-generated code.

## Pricing

Tiered SaaS, pricing not extensively published; Free + Pro + Enterprise structure.

## Differentiators

- **Self-healing on UI change.** The biggest practical win — kills the "every UI refactor breaks every E2E test" problem.
- **Natural-language authoring.** Lower barrier to entry for PMs and QA than Playwright/Selenium.
- **Verification framing.** Pitches against the AI code-gen boom — "you'll need more tests, not fewer, in the LLM era."

## Risk factors

- [[QA Wolf]] sells outcomes (coverage guarantees); Momentic sells software (you do the work). Different buyers.
- Self-healing only works until it doesn't — silent test rot is a real failure mode.
- Competes with horizontal E2E vendors (Playwright Test, Cypress, BrowserStack adding AI features).

## See also
- [[QA Wolf]]
- [[Tusk]]
- [[Antithesis]]
- [[Specialty Agents]]
