---
tags: [tool, docs, ai-agent, distribution-layer, specialty-agent]
created: 2026-05-28
---

# Mintlify

Mintlify is the dominant documentation platform for AI-era API companies. By late 2025 it had 10,000+ customer companies (up from ~1,000 two years prior), $10M ARR (10x YoY), and a customer list that reads as the who's who of LLM startups — Anthropic, Microsoft, Coinbase, and most YC AI companies use it. A $45M Series B at a $500M valuation, led by a16z and Salesforce Ventures, validated the docs-as-distribution-layer thesis.

## Origin

Founded in 2021 by Han Wang and Hahnbee Lee (Stanford alumni). Started as a simple docs-as-code generator before adding AI search, RAG, and analytics. Y Combinator alum.

## Funding & Traction

- Total raised: $67M.
- Series A (Feb 2024): $18.5M led by Bain Capital Ventures.
- Series B (2025): $45M led by Andreessen Horowitz and Salesforce Ventures at $500M valuation.
- ARR: $10M at end of 2025 (10x growth YoY from $1M).
- 10,000+ customer orgs.
- Notable customers: Anthropic, Microsoft, Coinbase, Cursor, Resend, Perplexity.
- Acquired RAG infrastructure company Trieve in July 2025 to bring chat infra in-house.

## Product

Mintlify is a docs-as-code platform:

1. **Docs hosting.** Connect a Git repo with MDX docs, get a branded site with search, custom domain, interactive components.
2. **AI Assistant.** Chat widget on every docs site. Uses RAG over docs to answer questions, generate code examples, cite sources. ~1M+ AI queries per month across customer base.
3. **AI authoring tools.** Generate first-draft docs from OpenAPI specs and codebases.
4. **Analytics.** Track what users search for, what answers are unhelpful — feeds back into docs improvement.
5. **CI integration.** Every commit syncs, previews on PRs, linting on broken links.

## Pricing

- Free tier.
- Pro: ~$150/month per docs site.
- Enterprise: custom (most large customers are on Enterprise).

## Differentiators

- **The default docs choice for AI-native companies.** Network effect — buyers see Anthropic and Coinbase using it, default to it.
- **AI search/chat over docs.** Better than DIY chatbots because RAG infra is purpose-built.
- **Acquired Trieve.** Now owns the RAG stack rather than depending on third parties.
- **Docs-as-code.** Engineers like that docs are Markdown in Git, not in a separate CMS.

## Risk factors

- ReadMe, GitBook, Docusaurus all compete. ReadMe especially has deeper API reference features.
- Customer concentration: a small number of LLM-cohort buyers drive disproportionate revenue.
- AI search/chat is becoming table stakes; differentiation will shift to authoring and analytics.

## See also
- [[Driver.ai]]
- [[Unblocked]]
- [[Pieces for Developers]]
- [[Specialty Agents]]
