---
tags: [concept, model]
created: 2026-05-28
---

# Reasoning Models for Code

The class of LLMs that spend extra inference-time compute on chain-of-thought before emitting a response — OpenAI's o1/o3/GPT-5 family, Anthropic's reasoning-mode Claude (Opus/Sonnet with extended thinking), Google's Gemini Deep Think, DeepSeek R1, Qwen QwQ. For coding, they trade latency for accuracy on hard problems where one-shot models hallucinate. Their arrival in late 2024 reshaped the ADE harness landscape, and they're the engine behind every viable [[Long-Horizon Coding]] product.

## The Tradeoff

| Dimension | Fast model (Sonnet, GPT-4o, Gemini Flash) | Reasoning model (Opus thinking, o3, GPT-5, R1) |
|---|---|---|
| Latency | Sub-second to few seconds | 10s to minutes |
| Cost | Low | 5–20x higher per task |
| Accuracy on hard problems | Mediocre | Strong |
| Use case | Autocomplete, inline edits, simple agents | Planning, debugging, long-horizon work |

## How ADEs Use Them

Most production agents now run a **two-model harness**:
- A fast model for tool-call dispatch, simple edits, autocomplete.
- A reasoning model for planning, debugging, multi-step tasks.

- **[[Aider]]** — `--architect` flag pairs a reasoning planner with a fast executor.
- **[[Cursor]]** — Composer routes hard requests to reasoning models; tab completion stays on a fast in-house model.
- **[[Cline]]** — model picker per mode (Plan vs Act); users typically pair Sonnet/Haiku.
- **[[Devin]]** — internally uses reasoning models for plan steps; fast models for execution.
- **[[Claude Code]]** — defaults to a reasoning-capable Claude with an explicit "thinking" hint via the `--thinking` flag and `/think` slash commands.

## What Reasoning Unlocked

- **SWE-bench Verified saturation** — o1 + Devin took SWE-bench from ~20% to >50% in 6 months; subsequent reasoning models pushed it to >93%.
- **Multi-step debugging** — reasoning models can hold a hypothesis tree across 10+ tool calls without losing thread.
- **Plan quality** — plans from reasoning models are markedly tighter; fewer steps, fewer dead ends.
- **Long-horizon viability** — without reasoning, agents collapse on tasks >30 minutes. With reasoning, hours become feasible.

## What Reasoning Didn't Solve

- **Context decay** still kills sessions after several hours; reasoning helps but doesn't fix.
- **Hallucination at the edges** — reasoning models still confidently invent APIs that don't exist.
- **Cost** — running an entire agentic loop on reasoning models is uneconomical for most workflows.
- **Latency** — reasoning models are bad fits for inner-loop work; user can't wait 30 seconds for autocomplete.

## The Routing Problem

The best harness picks the right model per turn. This is increasingly automated:
- Cursor and Windsurf route based on prompt characteristics.
- Claude Code uses Claude Sonnet/Opus model differentiation.
- Aider exposes the choice explicitly to the user via flags.
- [[Cerebras]] and [[Groq]] sell custom-silicon inference for reasoning models at unusual speeds — Cerebras claims 2000+ tok/s on Claude — making reasoning approach interactive latencies.

## See Also
- [[Agent Harness]]
- [[Long-Horizon Coding]]
- [[Plan Mode]]
- [[SWE-bench and Coding Benchmarks]]
- [[Cerebras]]
- [[Groq]]
