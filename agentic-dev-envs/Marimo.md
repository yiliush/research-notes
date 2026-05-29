---
tags: [tool, notebook-agent, open-source, python, ade-adjacent]
created: 2026-05-28
---

# Marimo

Marimo is the next-generation Python notebook that took Jupyter's failure modes — hidden state, broken cell ordering, non-reproducible execution, `.ipynb` JSON that doesn't diff — and rebuilt them away. Notebooks are stored as pure Python files, execution is reactive (cell A's value changes, dependent cells re-run), and the editor is explicitly designed for AI agents to drive it via a coordination protocol called marimo pair. By 2026 it is the notebook that AI-coding agents actually prefer, because it has a stable dataflow graph instead of mutable session state.

## Origin
- Founded 2023 by Akshay Agrawal (ex-Stanford, ex-Google Brain) and Myles Scolnick.
- Open source under Apache-2.0; primary repo marimo-team/marimo.
- Backed by funding from the angel/early-stage data infrastructure community (founders public about prioritising OSS-first development).
- 2025 inflection point: PyCon 2025 talk, --mcp flag for MCP bridging, marimo pair shipped as an agent-skill, marimo-agents experimental extension.

## Adoption
- GitHub stars in the tens of thousands by mid-2026, growing fast among data scientists and ML practitioners frustrated with Jupyter.
- Adopted as the notebook layer inside several research labs and ML teams that previously used Jupyter or Hex.
- Distribution mostly through OSS channels: PyPI install, GitHub, Hacker News, PyCon.

## Product
- Reactive execution — Marimo builds a dataflow graph from the cells; changing one re-runs dependent cells (or marks them stale). No more "did I run that cell?" debugging.
- Pure-Python file format — `.py` files, not JSON. Git diffs work. You can also execute a notebook as a script.
- Built-in package management.
- Native SQL support — embed SQL cells alongside Python.
- App mode — deploy a notebook as an interactive app (FastAPI/wasm) without a rewrite.
- Marimo pair — an agent skill that gives Claude Code, Codex, OpenCode and other agent CLIs full control of a running marimo session: read live variables, run cells, install packages, edit code.
- --mcp flag — exposes the notebook as an MCP server so any MCP-aware agent can drive it.
- Marimo-agents (experimental) — AI agents as first-class cells in the notebook, alongside Python and SQL.

## Pricing
- Free, open source. No paid SaaS as of May 2026.
- Marimo Cloud (in development) — hosted, multiplayer, team-managed version expected as the eventual revenue path.

## Differentiators
- Agent-native by construction — the dataflow graph and pure-Python format are exactly what an agent needs to reason about and modify a notebook. Hex Magic operates inside a notebook; Marimo IS the notebook designed to be agent-controlled.
- OSS-first against Hex's SaaS-first stack; commercial offering deferred.
- The Jupyter replacement story — the only project with technical credibility to argue Jupyter should be retired, not augmented.
- Risk: monetization timing. Marimo Cloud needs to ship before Hex extends down-market or Databricks/Snowflake commodify the notebook layer.

## See Also
- [[Notebook Agents]]
- [[Hex Magic]]
- [[Databricks Genie]]
- [[Model Context Protocol (MCP)]]
- [[Claude Code]]
