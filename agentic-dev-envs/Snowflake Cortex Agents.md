---
tags: [tool, notebook-agent, hyperscaler, data-tooling, ade-adjacent]
created: 2026-05-28
---

# Snowflake Cortex Agents

Snowflake Cortex Agents are Snowflake's answer to Databricks Genie — planner-tool-LLM agents that orchestrate Cortex Analyst (structured SQL over semantic views) and Cortex Search (unstructured retrieval) to answer analytical questions inside the data cloud. Generally available November 2025. The April 2026 update collapsed the Analyst delegation step into direct SQL generation, materially improving accuracy and latency.

## Origin
- Snowflake founded 2012 (Sridhar Ramaswamy CEO as of 2024).
- Cortex AI launched 2023 as Snowflake's in-platform LLM/inference layer.
- Cortex Agents GA: November 4, 2025.
- Snowflake Intelligence — the broader umbrella for the analyst-facing surface — and Cortex Code (developer-facing) introduced alongside.
- April 13, 2026: improved SQL generation in Cortex Agents — agents now emit SQL directly against semantic views rather than calling Cortex Analyst as a separate tool, lowering latency and raising accuracy.

## Adoption
- $100M AI revenue run-rate disclosed by Snowflake at the end of 2025, ahead of internal projections.
- AI-related workloads influencing ~50% of new bookings as of late 2025.
- Cortex Code (the developer-facing sibling) saw >50% of customers actively using it within months of November 2025 launch.
- Cortex AI for Financial Services launched as a vertical packaging.

## Product
- Agent runtime — plan → tool selection → execute → respond. Tools can be Cortex Analyst (semantic-view SQL), Cortex Search (unstructured), LLM calls, stored procedures, UDFs.
- Cortex Analyst — semantic-view-aware text-to-SQL. Post-April-2026, agents bypass this as a separate service and generate SQL directly using the semantic view definition.
- Cortex Search — unstructured retrieval, integrated as a tool.
- Custom tools — stored procedures and UDFs are first-class agent tools, which lets enterprises wire in their own logic and policy checks.
- Snowflake Intelligence — the analyst-facing chat surface that consumes Cortex Agents.
- Model access — GPT-5.2 and other frontier models available on Cortex AI as of late 2025.

## Pricing
- Consumption-based — Snowflake credits per inference call, per token, per Cortex Search query.
- Bundled into existing Snowflake account; no separate SKU for Cortex Agents.

## Differentiators
- Tool-using planner architecture is more explicitly agentic than Genie's flow-shaped design — Cortex Agents feel closer to a general agent framework with Snowflake-shaped tools.
- Custom tools via stored procedures and UDFs is the closest thing to MCP among the hyperscaler data agents.
- Semantic-view-first means the trust story flows through the existing Snowflake governance model.
- Less multi-agent coordination than Databricks Genie's 2026 stack — Snowflake's bet is on a strong single planner with good tools rather than on multi-agent orchestration.

## See Also
- [[Notebook Agents]]
- [[Databricks Genie]]
- [[Hex Magic]]
- [[Model Context Protocol (MCP)]]
