---
tags: [tool, code-review, ai-agent, specialty-agent]
created: 2026-05-28
---

# CodeRabbit

CodeRabbit is the breakout AI code review company of this cycle — by April 2026 it reportedly hit $40M ARR, up roughly 700% year-over-year, and locked in a $60M Series B at a $550M valuation. The product reads every pull request, leaves line-by-line commentary, and ships one-click fixes. It's the number one application on the GitHub Marketplace by install count.

## Origin

Founded in 2023 by Harjot Gill (CEO, ex-Nutanix) and Gur Singh. The company emerged from the observation that AI code generation was about to flood the PR queue and human reviewers would not scale. CodeRabbit positioned itself as the "quality gate for AI coding" — explicitly leaning into the idea that the bots writing code need other bots reviewing it.

## Funding & Traction

- Total raised: $88M
- Series B (Sept 2025): $60M led by Scale Venture Partners, with NVentures (NVIDIA), CRV, Harmony Partners, Flex Capital, Engineering Capital, Pelion. Valuation $550M.
- ARR: ~$15M reported at Series B close, ~$40M by April 2026 per Sacra.
- Growth: 20% MoM at time of Series B; 10x YoY.
- Team: ~24 people when crossed $15M ARR — extreme capital efficiency.
- 8,000+ paying organizations; 100,000+ OSS projects use the free tier.

## Product

CodeRabbit sits on the PR webhook. When a PR opens, the bot:

1. Posts a summary of the change.
2. Walks line-by-line with suggestions on logic, style, security, performance.
3. Generates "1-click commit" patches the author can apply directly.
4. Engages in threaded conversation — you can argue with it like a reviewer.
5. Runs static analysis tools (Semgrep, etc.) under the hood and explains findings in plain English.

CodeRabbit also offers an IDE/CLI mode that lets developers run the review locally before pushing.

## Pricing

- Free for open source.
- Pro: $24/dev/month (was $15 historically; price has crept up).
- Enterprise: custom, with self-hosted option and SOC 2.

## Differentiators

- **Distribution.** Top of GitHub Marketplace gives it organic install velocity competitors cannot match.
- **Conversational PR experience.** Most competitors leave drive-by comments; CodeRabbit engages in back-and-forth.
- **Multi-model orchestration.** Routes different review tasks (summary, deep logic, security) to different LLMs.
- **Capital efficiency.** $15M ARR on ~24 people. Implies very high per-employee revenue and a real product, not a wrapper.

## Notable customers

Chegg, Groupon, Mercury, plus 8,000+ smaller orgs. The customer mix skews mid-market — not heavy enterprise (yet).

## Risk factors

- GitHub itself could ship native AI review and crush them. Copilot already has PR review features.
- [[Greptile]] and [[Diamond by Graphite]] are direct competitors with comparable funding.
- Price pressure from open-source [[Qodo Merge]] and CodeRabbit's own free tier.

## See also
- [[Greptile]]
- [[Diamond by Graphite]]
- [[Qodo Merge]]
- [[Bito]]
- [[Specialty Agents]]
