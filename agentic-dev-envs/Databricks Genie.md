---
tags: [tool, notebook-agent, hyperscaler, data-tooling, ade-adjacent]
created: 2026-05-28
---

# Databricks Genie

Databricks AI/BI Genie is Databricks's data agent — the analyst-facing surface that lets business users ask plain-language questions of governed warehouse data and get back SQL, charts, and (as of 2026) predictions. Generally available in 2025, the 2026 expansion turned Genie into a multi-agent system: a Research Agent for multi-step hypothesis testing, Inspect for self-correcting SQL, and integration with TabPFN for direct predictive queries inside conversational BI.

## Origin
- Databricks founded 2013 by the Apache Spark creators (Ali Ghodsi CEO).
- AI/BI Genie originated as the conversational layer on top of Databricks AI/BI dashboards (announced 2024).
- General availability declared in 2025 alongside the Genie Spaces concept (governed, scoped Q&A surfaces).
- Late 2025–early 2026: Research Agent, Agent mode, Inspect, Genie Conversation API GA, TabPFN integration.

## Adoption
- Distribution via Databricks's existing customer base — Fortune 500 data teams already on the lakehouse.
- Strong attach in regulated industries (finance, healthcare, retail) where the Unity Catalog governance story matters.
- No standalone Genie revenue disclosed; it ships as part of the platform.

## Product
- Genie Spaces — scoped Q&A surfaces tied to specific tables and semantic context; each Space has its own example queries and trust policies.
- Thinking steps — every answer shows how the prompt was interpreted, which tables were used, and a sample SQL skeleton.
- Clarifying-question loop — Genie asks before guessing when the semantics are ambiguous.
- Agent mode (2026) — multi-step reasoning, top-driver analysis on chart changes, prompt caching.
- Research Agent — extended reasoning loop for harder questions; runs hypotheses against the warehouse.
- Inspect — verifies its own generated SQL by writing smaller validation queries and rewriting the main query if needed.
- TabPFN integration — predictive queries (forecasts, what-ifs) framed in natural language, with Databricks assembling data + model behind the scenes.
- Genie Conversation API (GA) — programmatically start conversations, send questions, retrieve results.

## Pricing
- Bundled into Databricks platform pricing — consumption of compute (DBUs) plus the AI/BI add-on.
- No public per-seat price; Enterprise sales motion.

## Differentiators
- Lakehouse-native — Genie sits directly on Unity Catalog governance; row/column-level security and lineage flow into the agent without extra work.
- Multi-agent under the hood — Research Agent + Inspect + TabPFN is the most coordinated multi-agent setup among the data-agent vendors as of mid-2026.
- Predictive-in-BI is novel — most data agents stop at descriptive analytics; Databricks routing to TabPFN inside the same conversational surface is a real differentiator vs Snowflake Cortex Agents.
- Lock-in cuts both ways — only available if your data lives in Databricks. Hex and Cosmic-class tools are warehouse-neutral.

## See Also
- [[Notebook Agents]]
- [[Snowflake Cortex Agents]]
- [[Hex Magic]]
- [[Marimo]]
