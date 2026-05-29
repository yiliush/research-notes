---
tags: [cluster, notebook-agent, data-tooling, ade-adjacent, surface-category]
created: 2026-05-28
---

# Notebook Agents

The Jupyter notebook — the dominant tool for data science, ML research, and analytics for a decade — is being eaten by AI agents from two directions: agentic copilots that drive existing notebooks (Hex Magic, Marimo pair, Google Colab's Data Science Agent) and conversational data agents that bypass the notebook entirely for governed warehouse data (Databricks Genie, Snowflake Cortex Agents). The category sits adjacent to the main ADE cluster because the surface is a notebook, not an IDE — but the underlying agent loop is the same.

## Why It Belongs In This Vault

Data work is the second-largest professional codebase activity after web/app development, and unlike app development it has been historically organized around the notebook rather than the file. Agents that can drive a notebook — read cells, write SQL, fix errors, generate charts, narrate findings — turn into the productivity wedge analysts feel most directly. By mid-2026, every major data tooling vendor has shipped one.

## The Two Architectures

**Notebook-native.** [[Hex Magic]] and [[Marimo]] operate inside a notebook. The agent reads existing cells, the schema, the semantic model, and prior context; it proposes and runs new cells; the human reviews and edits. The unit of work is still the cell. Marimo's bet is that the notebook itself needs redesigning (reactive execution, pure-Python file format) so agents can drive it cleanly. Hex's bet is that the cell-and-thread workflow is fine, but agents need a strong semantic grounding layer.

**Warehouse-native.** [[Databricks Genie]] and [[Snowflake Cortex Agents]] live above the warehouse, not inside a notebook. Users ask questions in natural language, the agent plans, executes SQL, returns results. The notebook surface is optional — a chat UI is the default. The trust anchor is the warehouse's governance (Unity Catalog, Snowflake row-level security) and the semantic layer (Cortex Analyst semantic views, Databricks's semantic models).

## What Distinguishes The Vendors

- **Hex Magic** — multi-warehouse, multiplayer-first, semantic-model-centric, mid-market and enterprise.
- **Marimo** — OSS, agent-friendly notebook redesign, no SaaS yet, developer-first.
- **Databricks Genie** — lakehouse-native, most coordinated multi-agent stack (Research Agent + Inspect + TabPFN for predictive-in-BI).
- **Snowflake Cortex Agents** — tool-using planner architecture, custom tools via stored procedures, semantic-view-first.

## The Predictive Frontier

Most data agents stop at descriptive analytics — "what happened, what's the breakdown, why did this change." [[Databricks Genie]]'s 2026 integration with TabPFN extended the surface to predictive queries in natural language inside conversational BI ("what's our forecast next quarter, what happens if we cut prices 5%"). This is the direction the category moves: from "talk to your data" to "ask your data to predict."

## Why Jupyter Doesn't Have An Agent Story

Jupyter's hidden-state, JSON-file, non-reactive execution model is the structural reason Marimo exists. Agents need predictable, addressable, diff-friendly notebooks; Jupyter notebooks are none of those. The Project Jupyter ecosystem has copilots (Jupyter AI, GitHub Copilot in JupyterLab) but no agent-native redesign. This is Marimo's wedge.

## Entities

- [[Hex Magic]] — Hex's in-notebook AI; Notebook Agent + Threads + Semantic Model Agent
- [[Marimo]] — reactive, agent-native OSS notebook with Marimo pair
- [[Databricks Genie]] — lakehouse-native, multi-agent including predictive
- [[Snowflake Cortex Agents]] — warehouse-native planner + tools

## See Also
- [[Vibe Coding]]
- [[Model Context Protocol (MCP)]]
- [[Market Landscape]]
