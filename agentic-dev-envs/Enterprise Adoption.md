---
tags: [market]
created: 2026-05-28
---

# Enterprise Adoption

By mid-2026 the question is no longer whether enterprises adopt AI coding tools — it is which tools, on which procurement vehicle, and whether the productivity gains justify the per-seat costs. Adoption is near-universal in big tech, deep in financial services, and meaningful in regulated industries. The productivity evidence is contested but trending positive after a year of methodological debate.

## Penetration by Vendor

**GitHub Copilot.** ~90% of Fortune 100 use Copilot (Microsoft, FY2025 earnings). 50,000+ paying organizations. 4.7M paid seats as of January 2026 (75% YoY growth). Among industry verticals: ~90% of large tech firms, ~80% of banks/financial services teams, ~70% of major insurers report Copilot deployments (composite of analyst surveys, Q1 2026).

**Cursor for Business.** Cursor's enterprise tier crossed major adoption thresholds across late 2025-early 2026. The April 2026 round to $50B valuation was reportedly catalyzed by enterprise growth surges (TechCrunch). Customers include Stripe, Shopify, OpenAI, Mercado Libre, Instacart, NVIDIA. Pricing: $40/user/mo Business, custom Enterprise. Cursor's $2B ARR is largely enterprise-driven.

**Cognition / Devin.** Devin's enterprise plan offers VPC deployment, SAML/OIDC SSO, custom Devins. Combined Devin + Windsurf enterprise ARR is up >30% post-acquisition (Cognition, Aug 2025), with 350+ enterprise customers inherited from Windsurf. Devin is sold to engineering leaders as an autonomous agent, not a pair-programmer.

**Claude Code.** Ships only in Team Premium ($100/seat, 5-seat min) or Enterprise. Average enterprise customer: $150-250/dev/month, ~$13/dev/active day. 90% of users stay below $30/active day. Anthropic does not publicly disclose Claude Code seat counts but it is reportedly Anthropic's fastest-growing product line.

**AWS Q Developer.** Wound down in 2026 — new signups blocked May 15, 2026 — and migrating customers to Kiro. Amazon internally reported $260M in cost savings and "4,500 developer years saved" from Q-assisted modernization (AWS blog), the largest first-party productivity claim from any hyperscaler.

## Productivity Evidence: The METR Saga

The most-cited study and the most contested. METR (Model Evaluation & Threat Research) ran a randomized controlled trial on experienced open-source developers in early 2025.

**Original result (July 2025):** Developers were 19% slower with AI tools (Cursor Pro + Claude 3.5/3.7 Sonnet), even though they self-reported being 20% faster. 246 tasks, 16 developers. 95% CI: -40% to -2%. This became the canonical "AI coding tools don't help experts" citation.

**Update (February 2026):** METR re-ran with 800+ tasks across 57 developers after discovering a selection bias — 30-50% of original invitees declined participation without AI access. The follow-up showed -4% slowdown with CI -15% to +9%. METR concluded "AI likely provides productivity benefits in early 2026." This rehabilitation was less covered than the original headline.

**Industry surveys.** Stack Overflow 2024: 76% of developers use or plan to use AI tools. JetBrains 2025: ~80% of companies allow third-party AI tools. DX/GitClear data through 2025 showed productivity gains concentrated at junior developers and on greenfield work; experienced developers on legacy code saw smaller or negative effects.

**Synthesis (mid-2026).** The honest reading: AI coding tools deliver modest to substantial productivity gains for most teams, with high variance by task type, codebase maturity, developer seniority, and harness sophistication. The "free 30% velocity" narrative of 2024 is dead. The "AI makes seniors slower" narrative of mid-2025 is also dead.

## Procurement Patterns

**SOC 2, data residency, no-training clauses.** Standard requirements by mid-2026. Cursor, Cognition, Anthropic, OpenAI all offer Enterprise terms that include zero-data-retention and no-training-on-customer-code. Anthropic publishes the strongest defaults; OpenAI requires Enterprise tier for equivalent guarantees.

**The "Copilot + one specialist" pattern.** Most large enterprises run Copilot as the default seat (cheap, broadly deployed, satisfies "we have AI coding tools" mandate) and pay for one or two specialist tools — Cursor or Claude Code for power users, Cognition Devin for autonomous workflows, Cody or Sourcegraph for code intelligence. Few enterprises consolidate on a single vendor.

**Token routing.** Enterprises with their own Anthropic / OpenAI / Bedrock contracts route inference through existing commits rather than re-paying through an ADE seat. This drives BYOK demand and is why Cline, Aider, and Continue have meaningful enterprise pull despite being free.

**Self-hosting.** Defense, finance, and healthcare procurement increasingly requires on-prem or VPC-hosted agents. Cline Teams, Cognition VPC deployment, and OpenHands self-hosted are the explicit answers; Continue and Aider serve customers who need to wire their own.

## See Also
- [[Market Landscape]]
- [[Pricing Models]]
- [[Competitive Dynamics]]
- [[Codebase Indexing]]
- [[Agent Harness]]
