---
tags: [tool, notebook-agent, analytics, ade-adjacent, data-tooling]
created: 2026-05-28
---

# Hex Magic

Hex Magic is the in-product brand for Hex's AI layer; the Notebook Agent that launched in August 2025 is what turned Hex from "the collaborative SQL/Python notebook for data teams" into a serious agentic surface for analysts. By the Fall 2025 launch, the same agent framework also shipped as Threads (conversational self-serve) and the Semantic Model Agent, all riding on top of Hex's existing index of warehouse tables, semantic models, and notebooks.

## Origin
- Hex Technologies founded 2019 by Barry McCardel, Caitlin Colgrove, and Glen Takahashi (ex-Palantir Foundry).
- HQ San Francisco. Backed by Sequoia, a16z, Amplify, Redpoint.
- "Magic" started as the brand for the autocomplete/SQL-generation layer (2023); the Notebook Agent rebrand in 2025 is when the product became agentic rather than copilot-shaped.
- Fall 2025 launch described by Hex as "probably our biggest release ever" — Threads, Notebook Agent, Semantic Model Agent shipped together.

## Adoption
- "Thousands of data teams" using the Notebook Agent daily per Hex's late-2025 disclosures.
- Reference customers public on the site include ramp, Anthropic, Reddit, Notion, ClickUp, Wayfair, Mercor.
- The Mercor case study on pricing analysis is the canonical Notebook Agent deployment story.

## Product
- Notebook Agent runs inside a Hex notebook — reads the existing cells, schema, semantic model, and prior threads; proposes SQL/Python cells; runs them; iterates on errors; writes commentary and chart specs.
- Threads — chat-style interface on the same agent framework, aimed at non-analysts asking questions in plain language against governed semantic models.
- Semantic Model Agent — helps maintain and extend the semantic layer, which is the trust anchor for the other two surfaces.
- Multi-language: SQL, Python, R inside the same notebook; agents can mix.
- Built-in connectors to Snowflake, Databricks, BigQuery, Redshift, Postgres, and the major SaaS sources.

## Pricing
- Free tier for individuals (limited usage, public notebooks).
- Team plan ~$24/user/month.
- Enterprise — custom; the Notebook Agent and Semantic Model Agent are pitched as Enterprise-tier flagship features.

## Differentiators
- Notebook-native — Hex Magic doesn't replace the notebook; it operates inside it. Cells are the unit, version control and diff review work as expected, analysts can edit any cell the agent writes.
- Semantic model integration — Hex's bet is that the agent is only as good as its grounding; the Semantic Model Agent feeds the other agents.
- Multi-source by design — unlike Genie (Databricks-native) and Cortex Agents (Snowflake-native), Hex sits above any warehouse.
- Collaborative DNA — Hex was multiplayer-first; the agent inherits multiplayer review, comments, and approvals out of the box.

## See Also
- [[Notebook Agents]]
- [[Marimo]]
- [[Databricks Genie]]
- [[Snowflake Cortex Agents]]
- [[Vibe Coding]]
