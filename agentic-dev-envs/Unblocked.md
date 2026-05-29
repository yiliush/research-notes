---
tags: [tool, onboarding, repo-intelligence, ai-agent, specialty-agent]
created: 2026-05-28
---

# Unblocked

Unblocked (getunblocked.com) is the codebase context agent for the rest of the team — not just the developer touching the code, but the PM, designer, or new hire who needs to understand how something works. It ingests code, docs, Slack, Jira, Confluence, and GitHub history and answers questions about any of it with citations. Closest to a "Glean for engineering" pitch.

## Origin

Founded by Dennis Pilarinos, who previously built Buddybuild (acquired by Apple in 2018) and held director roles at Microsoft Azure and AWS. Strong devtools provenance — buyers trust him to build infrastructure that lasts.

## Funding & Traction

- Total raised: $30M.
- Series A (May 2025): $20M led by B Capital and Radical Ventures.
- Prior seed funding from Amplify Partners, First Round Capital, XYZ Capital.

## Product

Unblocked synthesizes context from:

- Code (GitHub, GitLab, Bitbucket).
- Docs (Confluence, Notion, internal docs).
- Chat (Slack).
- Tickets (Jira, Linear).
- Code history (commit messages, PRs).

When asked a question, it:

1. Searches across all sources.
2. Reconciles conflicting information ("the README says X but the recent Slack thread says Y").
3. Enforces permissions — users only see results they have access to.
4. Ranks by relevance and recency.

Used for onboarding, context for incidents, "what does this code do" questions.

## Pricing

21-day trial of Code Review and Platform plans. Paid tiers exist but specific pricing varies — sales-led for enterprise.

## Differentiators

- **Multi-source synthesis.** Most repo-intelligence tools just index code. Unblocked correlates code with the conversations around it.
- **Permissions-aware.** Critical for enterprise — answers respect ACLs.
- **Founder pedigree** in dev tools infrastructure.

## Risk factors

- [[Greptile]] is doing similar codebase Q&A as a side-effect of their PR review product.
- Glean (horizontal enterprise search) is moving into engineering-specific use cases.
- Sales cycle for cross-team tools is longer than developer-only tools.

## See also
- [[Greptile]]
- [[Sourcegraph]]
- [[Mintlify]]
- [[Pieces for Developers]]
- [[Specialty Agents]]
