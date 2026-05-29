---
tags: [tool, code-review, repo-intelligence, ai-agent, specialty-agent]
created: 2026-05-28
---

# Greptile

Greptile is the codebase-aware code reviewer. Where most PR bots reason about the diff in isolation, Greptile builds a graph index of the entire repository — files, functions, calls, dependencies — and uses multi-hop traversal to surface bugs that span files. It reviews 500M+ lines of code per month and counts Brex, Substack, PostHog, Bilt, and Y Combinator's internal team as customers.

## Origin

Founded in 2023 by Daksh Gupta, fresh out of Georgia Tech, through Y Combinator W24. Gupta was vocal early about "996" working culture and turned Greptile into a viral founder brand on X. The product originated as a generic "talk to your codebase" API before pivoting to focus on PR review as the highest-leverage entry point.

## Funding & Traction

- Total raised: ~$29M.
- Seed (2024): $4M from Initialized Capital and YC.
- Series A (Sept 2025): $25M led by Benchmark (Eric Vishria joined board). Continued Cory Levy, Y Combinator, Initialized. Valuation reported at $180M during talks.
- Reviews ~500M lines of code/month per company-cited figures.
- Notable customers: Brex, Substack, PostHog, Bilt, YC internal.

## Product

Greptile 3 (the current version as of late 2025) does three things:

1. **Codebase indexing.** Constructs a semantic + structural graph of the entire repo. Takes 1–2 hours on a very large monorepo.
2. **PR review.** When a PR opens, Greptile uses multi-hop reasoning across the index to catch logic bugs that require understanding code far from the diff.
3. **Codebase Q&A.** Same index, exposed as a chat interface — engineers query "how does auth work in this repo?" and get cited answers.

The index itself is the moat. Competitors who only read the diff cannot catch the same class of cross-file bugs.

## Pricing

- Free tier for personal/small use.
- Team: $30/dev/month.
- Enterprise: custom, includes self-hosted indexing.

## Differentiators

- **Graph index of the codebase.** The deepest repo intelligence layer in the cluster.
- **Multi-hop reasoning.** Will trace a variable across three files to verify a contract is held.
- **Founder/brand velocity.** Greptile has the strongest social presence of the code review specialists, which feeds top-of-funnel.

## Risk factors

- [[CodeRabbit]] has 5x the ARR and twice the funding. Greptile must justify "smarter" reviews vs. CodeRabbit's distribution.
- Index-building is expensive infra; margin pressure as token costs fluctuate.
- [[Sourcegraph]] has been doing code-graph indexing for a decade and could pivot Amp into the same lane.

## See also
- [[CodeRabbit]]
- [[Diamond by Graphite]]
- [[Sourcegraph]]
- [[Unblocked]]
- [[Specialty Agents]]
