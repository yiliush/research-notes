---
tags: [tool, code-review, ai-agent, open-source, specialty-agent]
created: 2026-05-28
---

# Qodo Merge

Qodo Merge — formerly Codium PR-Agent — is the open-source pull-request reviewer that grew into a commercial code-quality platform. The underlying repo `qodo-ai/pr-agent` has ~10,700 GitHub stars, making it the most-starred OSS PR review tool. The company behind it, Qodo (formerly CodiumAI), raised $40M in Series A and now ships testing, IDE, and CLI agents around the same brand.

## Origin

CodiumAI was founded in 2022 by Itamar Friedman (CEO, ex-Alibaba) and Dedy Kredo. The company first launched a test-generation tool, then open-sourced PR-Agent in 2023 which became the breakout product. Rebranded to Qodo in 2024 to consolidate the agent suite (Qodo Gen, Qodo Cover, Qodo Merge).

## Funding & Traction

- Total raised: ~$50M.
- Series A (Sept 2024): $40M led by Susa Ventures with Square Peg, Vine Ventures, ICON, others.
- Open-source repo: ~10,700 stars on GitHub, 1,400 forks, 200+ contributors.
- Customers include Snowflake, AT&T, BNP Paribas, JFrog.

## Product

Two layers:

1. **PR-Agent (OSS).** Self-hostable PR reviewer. Configure with a YAML, point at your GitHub/GitLab webhook, get reviews. Fully under your infra; you bring your own LLM key.
2. **Qodo Merge (commercial).** Managed SaaS version + additional features: codebase-aware review using their proprietary indexing, custom rules, smart suggestions tracked over time, Confluence/Jira integration, enterprise security.

Adjacent products in the suite: **Qodo Gen** (IDE plugin for code generation), **Qodo Cover** (test generation), and a CLI agent.

## Pricing

- Developer (free): 30 PR reviews + 250 IDE/CLI credits per month.
- Teams: $30/user/month annual ($38 monthly).
- Enterprise: custom.
- PR-Agent OSS: free, self-host with own LLM costs.

## Differentiators

- **Open-source foundation.** Only major code reviewer with a real OSS path. Important for security-conscious enterprises that want to self-host.
- **Full SDLC agent suite.** Code gen + test gen + PR review under one roof. Closest specialist to a horizontal platform.
- **Israeli engineering provenance.** Strong showing in regulated/financial verticals.

## Risk factors

- [[CodeRabbit]] is winning the hosted-SaaS PR review market on UX and distribution.
- The multi-product strategy dilutes positioning vs. focused specialists like [[Greptile]] (review) or [[Tusk]] (tests).
- OSS PR-Agent has slowed — community maintenance is unclear after Qodo's commercial push.

## See also
- [[CodeRabbit]]
- [[Greptile]]
- [[Tusk]]
- [[Specialty Agents]]
