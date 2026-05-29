---
tags: [tool, open-source, agent-framework, huggingface, ade-cluster]
created: 2026-05-28
---

# smolagents

smolagents is Hugging Face's minimalist agent library — about 1,000 lines of code total — built around the thesis that agents should write their actions as executable Python rather than JSON tool calls. Launched December 2024, it grew from ~3k to ~27.6k GitHub stars by May 2026, making it one of the fastest-growing agent frameworks in the OSS ecosystem. Not a "smol developer" successor (despite the name collision); it's a substrate library that powers other people's coding agents.

## Origin
- Created at Hugging Face, public launch December 5, 2024. Primary maintainers: Aymeric Roucher, Albert Villanova del Moral, Thomas Wolf (HF co-founder), Leandro von Werra, Erik Kaunismäki.
- Builds on HuggingFace's earlier "transformers agents" experiment but is a clean-room rewrite around CodeAgents.
- Thesis citation: HF's blog post argued code-based actions use ~30% fewer steps than JSON tool calls on benchmarks like GAIA. This finding partly reproduced earlier work from CodeAct (Wang et al.) but smolagents was first to package it as a popular library.
- Naming confusion: distinct from Smol AI / "smol developer" by Swyx (2023), which was a separate viral repo. The HF library inherited the "smol" aesthetic but not the code.

## Adoption
- GitHub stars verified May 2026: ~27.6k.
- Tens of millions of PyPI downloads cumulatively.
- Used as the underlying agent layer in research projects, hackathon submissions, and a handful of production OSS tools.
- Bundled CLI tools: `smolagent` (general agent), `webagent` (browser-using agent).

## Architecture
- Two agent types: `CodeAgent` (writes Python) and `ToolCallingAgent` (classic JSON tool calls).
- Sandboxed execution backends: E2B, Blaxel, Modal, Docker, Pyodide+Deno WebAssembly. Choose the threat model.
- Model-agnostic via LiteLLM, transformers, Ollama, or any Hub-hosted model.
- Modalities: text, vision, video, audio.
- Hub integration: agents and tools can be pushed/pulled as Hub repos.
- MCP server support and LangChain tool compatibility.
- License: Apache-2.0.

## Pricing
- Free, OSS. Hugging Face monetizes adjacent products (Inference Endpoints, Spaces) rather than the library itself.

## Differentiators
- "Agents that think in code" is its slogan and its bet — code as the action language is more expressive than JSON tool calls and composes naturally with loops, conditionals, error handling.
- The ~1,000-line constraint is enforced by maintainers as a design discipline. Compare to LangChain (hundreds of thousands of LOC).
- Sandbox backend pluggability is the most complete in any OSS agent framework.
- Distribution advantage: comes pre-blessed by HF, which means visibility in the default "what library do I pick" search for ML/AI devs.

## Strategic Position
- Not a direct ADE competitor — it's the substrate other coding agents can build on.
- Closest comparison: LangChain's agents module (heavyweight) and Microsoft's Autogen (research-y). smolagents wins on minimalism.
- The unanswered question: will agent frameworks matter at all once Anthropic, OpenAI, and Google ship their own framework-level abstractions (Claude Agent SDK, OpenAI Agents SDK)? smolagents bets on the cross-provider seam staying valuable.

## See Also
- [[Open Interpreter]] — code-execution-first cousin
- [[Aider]] — coding-specific
- [[Model Context Protocol (MCP)]]
- [[Agent Harness]]
- [[Green Shoots]]
