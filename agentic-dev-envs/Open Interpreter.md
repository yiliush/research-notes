---
tags: [tool, open-source, agent-adjacent, scrappy, ade-cluster]
created: 2026-05-28
---

# Open Interpreter

Open Interpreter is the original "natural language interface for computers" — an open-source project by Killian Lucas that lets an LLM execute Python, JavaScript, shell, and browser actions locally on a user's machine. It went viral in September 2023 (20k+ stars in its first week, then one of the top trending GitHub repos of the year) and remains one of the most-starred AI agent projects ever despite never raising venture funding. By May 2026 it sits at ~63.7k stars but its center of gravity is more "personal computing agent" than "coding agent," which puts it adjacent to — not inside — the ADE category.

## Origin
- Created by Killian Lucas, open-sourced September 2023.
- Initial framing was deliberately anti-corporate: "ChatGPT's Code Interpreter, but on your own machine." This contrast was load-bearing — at the time OpenAI's Code Interpreter ran in a sandboxed VM with no internet and a 100MB file limit.
- Lucas remained solo-founder for over a year. The project incorporated as Open Interpreter, Inc. but stayed bootstrapped.
- Subsequent products: the **01 Light** (a Star-Trek-style voice device, crowdfunded 2024, shipped late) and **Open Interpreter Desktop** (a Mac app).

## Adoption
- GitHub stars verified May 2026: ~63.7k. Among the top 5 most-starred AI agent projects in history alongside AutoGPT, gpt-engineer, and MetaGPT.
- 3,120+ commits, active development.
- PyPI: hundreds of thousands of cumulative installs.
- Notably has *not* converted star count into enterprise revenue — Lucas has stayed product-focused rather than building a commercial layer.

## Architecture
- Python library + CLI; can run code in Python, JavaScript, Shell, AppleScript, R, PowerShell.
- Model-agnostic via LiteLLM: GPT-4o default, Claude, Gemini, Ollama, LM Studio, Llamafile all supported.
- Browser automation via Chrome control.
- Interfaces: terminal REPL, Python API, FastAPI server.
- Safety: requires user confirmation before each code block executes (configurable).
- License: AGPL-3.0 — notably copyleft; commercial users have to think carefully.

## Pricing
- Free, open-source. No hosted SaaS tier offered.

## Differentiators
- The signature project of a "personal AI" thesis — treats the LLM as a user, not a developer. Coding ability is incidental to filesystem control, browser automation, and media manipulation.
- AGPL choice is a deliberate fence against repackaging, in contrast to Aider's permissive Apache 2.0.
- Killian Lucas is one of the few solo founders whose tool reached top-trending GitHub status — he's a recurring figure in the indie-AI-agent community.
- Conceptual ancestor to projects like Anthropic's Computer Use API and OpenAI's Operator — Open Interpreter's "let the LLM control your machine" framing predates both by 18 months.

## Limitations as an ADE
- Not optimized for codebase indexing or large repo navigation — there's no equivalent of Cursor's index or Aider's repo-map.
- No IDE integration; no PR or diff workflow.
- "Run arbitrary code on the user's machine" is a security posture most enterprise dev teams reject outright.

## See Also
- [[Aider]] — coding-specific contemporary
- [[smolagents]] — minimal-framework cousin
- [[Goose]] — Block's competing personal-computing agent
- [[Green Shoots]]
