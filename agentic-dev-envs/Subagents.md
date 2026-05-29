---
tags: [concept, primitive, harness]
created: 2026-05-28
---

# Subagents

A primitive where a parent agent delegates a discrete task to a child agent with its own context window, tools, and lifetime. The child returns a result (and often a summary) to the parent; the parent's main context is preserved. Subagents are the leading mechanism for handling long-horizon coding tasks without blowing up the parent's context budget.

## Why They Exist

Single-context agents hit two walls:
1. **Context exhaustion** — investigating a 50-file codebase pollutes the main agent's working memory with grep results, file reads, and dead-end traces.
2. **Specialization** — the same model has to act as planner, coder, reviewer, debugger, in one role. Specialized prompts and tool subsets perform better.

Subagents solve both: spawn a child agent for "go investigate why this test is flaky," let it churn through 30 tool calls, return a 3-sentence summary. The parent never sees the noise.

## Implementations

- **[[Claude Code]]** — explicit `Agent` tool dispatch with sub-agent types (general-purpose, Explore, Plan, code-reviewer, etc.). Sub-agents can run in parallel and even in background. Among the most developed subagent system in any ADE.
- **[[Codex CLI]]** — parallel sub-agent support added in late 2025 GA.
- **[[OpenHands]]** — multi-agent system with planner / executor / reviewer agents native to the harness.
- **[[Devin]]** — internal multi-agent decomposition for long tasks; not user-facing.
- **[[Aider]]** — closest analogue is its `--architect` flag (strong-model planner / cheap-model executor), but it's not a full subagent system.
- **[[OpenAI Codex CLI]]** — added subagent dispatch via a parallel-task primitive.

## The Two Patterns

- **Investigative subagents** — dispatched to read, search, and report without writing. Used to compress 30K tokens of file reads into a 500-token summary. Claude Code's `Explore` agent is the canonical example.
- **Executive subagents** — given a self-contained task ("write the migration script") and authorized to write. Output is reviewed by the parent before integration. Higher risk; more common in async/autonomous agents than in inline CLI tools.

## Open Problems

- **Result hallucination** — subagent says "done" when it failed silently. Parents need verification, not trust.
- **Coordination overhead** — too many sub-agents and the parent becomes a project manager, not a coder.
- **Tool boundary** — should a sub-agent be allowed to write? Run shells? Spawn its own sub-agents? Most harnesses restrict.
- **Cost accounting** — sub-agent token spend is opaque; users blow through credit budgets without realizing the parent dispatched 10 children.

## Relationship to Parallel Agent Orchestrators

[[Parallel Agent Orchestrators]] like [[Conductor]] and [[Claude Squad]] are a *user-facing* form of multi-agent work — multiple top-level Claude Code sessions on multiple branches. Subagents are the *internal* form — one top-level session that internally fans out. Both patterns are converging: Conductor sessions increasingly dispatch subagents themselves.

## See Also
- [[Agent Harness]]
- [[Long-Horizon Coding]]
- [[Parallel Agent Orchestrators]]
- [[Claude Code]]
- [[OpenHands]]
