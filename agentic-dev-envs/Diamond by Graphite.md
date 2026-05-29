---
tags: [tool, code-review, ai-agent, specialty-agent]
created: 2026-05-28
---

# Diamond by Graphite

Diamond was Graphite's AI code reviewer, launched in 2024 to complement their stacked-PR workflow tool. As of late 2025, Diamond as a standalone product name was retired and folded into "Graphite Agent" — a broader AI offering bundled with every Graphite plan. The play: use the existing Graphite footprint among engineers who already love stacked PRs as a wedge to push AI review.

## Origin

Diamond was built by Graphite, founded in 2020 by Merrill Lutsky, Greg Foster, and Tomas Reimers (ex-Airbnb). Graphite's first product was a CLI and web UI for stacked diffs (multiple dependent PRs at once), a developer workflow popular at Meta and Google. Diamond was launched at Graphite's Series B in May 2024 to layer AI on top of that existing review surface.

## Funding & Traction

- Graphite Series B (May 2024): $52M led by Andreessen Horowitz, total funding ~$80M.
- Diamond launched concurrent with the Series B.
- Customers: Ramp, Vercel, Asana, Shopify (using Graphite's stacking workflow; Diamond rolls out across that base).

## Product

Graphite Agent (the rebranded Diamond) does:

1. AI PR review with codebase context — comparable to [[CodeRabbit]] and [[Greptile]].
2. AI chat embedded in the PR — engineers can ask the agent to explain or modify.
3. Integration with Graphite's stacking and merge queue features.

The differentiator is workflow: if you already use Graphite's stacked PRs, the AI agent has visibility into the whole stack, not just one PR.

## Pricing

- Free 30-day trial of Graphite Agent.
- Starter: $20/month — stacking + limited Agent.
- Team: $40/month — unlimited Agent reviews and chat, merge queue, advanced team features.
- Diamond was previously free up to 100 PRs/month standalone — that tier is gone.

## Differentiators

- **Bundled with stacked PRs.** The only major AI reviewer with a native stacked-PR workflow underneath. For teams who buy into stacking, Diamond is the lowest-friction reviewer.
- **Merge queue integration.** Reviews + merge orchestration in one tool.
- **Lower stated focus on individual review accuracy.** Graphite competes on workflow, not on "smartest reviewer."

## Risk factors

- Bundling forces customers to adopt Graphite's stacking workflow to get the AI features. Teams happy with vanilla GitHub PR flow will prefer [[CodeRabbit]] or [[Greptile]].
- Stacking is a niche workflow outside elite engineering orgs.
- Diamond name retirement suggests internal uncertainty about positioning.

## See also
- [[CodeRabbit]]
- [[Greptile]]
- [[Qodo Merge]]
- [[Specialty Agents]]
