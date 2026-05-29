---
tags: [concept]
created: 2026-05-28
---

# Agent Harness

An agent harness is the control loop around the LLM that turns a single inference call into a coherent task completion. Same model, different harnesses: very different agents. The 2-5 percentage point gap on SWE-bench between top model+harness pairings and the underlying raw model is almost entirely harness. By mid-2026 four canonical harness designs dominate — Aider's diff loop, Cline's plan/act, Devin's planner+executor, and Claude Code's todo+subagent — each with distinctive tradeoffs.

## What a harness is

At minimum, a harness handles:
- **Tool registration and dispatch.** Filesystem read/write, shell execution, search, web fetch.
- **The reason-act loop.** Model outputs a tool call → execute → model sees result → repeats.
- **Context management.** Truncate, summarize, or page memory across turns.
- **File-edit format.** Whole-file rewrite, search/replace, unified diff, line-range patch.
- **Error recovery.** Retry, replan, escalate to human.
- **Termination.** When does the agent decide the task is done?

A harness is a few hundred lines for a basic loop and thousands of lines for a production agent. The harness is also where most of the user-facing UX lives.

## Aider's diff loop (file-edit-centric)

Aider's harness is the most opinionated about one thing: code edits. It is designed around getting the LLM to produce clean, applicable diffs.

- **Edit format.** Several supported: whole-file, search/replace blocks, unified diffs. The format is tuned per model (different models reliably produce different formats).
- **Loop.** Single-pass for most tasks: the model proposes edits, Aider applies them, runs tests if configured, optionally re-prompts on failure.
- **Context.** A "repo map" — a token-budgeted symbol summary of the codebase derived via tree-sitter — gives the model awareness of files it hasn't loaded.
- **Git-native.** Every change is auto-committed; rollback is `git revert`.
- **Strengths.** Predictable, fast, model-agnostic. Excels on small, focused edits with clear specs.
- **Limits.** Single-shot bias; doesn't naturally explore the codebase or run multi-turn diagnostics.

## Cline's Plan/Act (two-mode dialog)

Cline split the agent loop into two explicit modes:

- **Plan mode.** Read-only. The agent explores the codebase, asks clarifying questions, proposes a strategy. Costs a fraction of the tokens of full execution.
- **Act mode.** Write/execute. The agent implements the agreed plan. Every file edit and terminal command surfaces a diff for user approval, with auto-approve toggleable.
- **Checkpoints.** Every step is checkpointed so the user can revert.
- **Multi-agent.** Cline's Kanban UI lets the user fan tasks across multiple isolated git worktrees; the agents work in parallel.
- **Strengths.** Catches misunderstandings before expensive execution. Gives the developer real review surface. Native MCP support.
- **Limits.** The mode-switch is friction. Power users complain it slows them down on tasks they can specify upfront.

## Devin's planner + executor (autonomous-first)

Cognition's Devin is built for autonomy — the developer assigns a task and walks away.

- **Planning agent.** Receives the task, produces a structured plan (multi-step, branchable), and updates the plan as the work progresses.
- **Executor agents.** Run in cloud sandboxes (see [[Cloud Sandboxes]]). Each step in the plan can spawn a sandboxed execution context.
- **Browser-using.** Devin can browse documentation, click through web UIs, drag files. This sets it apart from terminal-only agents.
- **Devin's UI** shows the plan, the current step, file diffs, the terminal, and the browser — all live.
- **ACU billing.** ~15 minutes of autonomous work per ACU; the harness budgets accordingly.
- **Strengths.** Genuinely async. Works overnight. Handles long, multi-stage tasks better than IDE-coupled agents.
- **Limits.** Less interactive — corrective feedback mid-run is harder. ACU bills can surprise.

## Claude Code's todo + subagent (Anthropic's reference design)

Claude Code's harness has become the most-imitated design of 2025-26.

- **Todo list.** The agent explicitly maintains a todo list for the task. Items are added, marked in-progress, completed. The list is visible to the user.
- **Subagents.** The main agent can spawn subagents for parallel or specialized work (e.g., a "search the codebase" subagent, an "implement and test feature X" subagent). Each subagent has its own context window and tool budget.
- **Primitive tools.** Read, Write, Edit, Bash, Grep, Glob, WebFetch. No precomputed codebase index — the agent navigates via these primitives.
- **Hooks.** User-defined shell scripts that fire on lifecycle events (PostToolUse, UserPromptSubmit, etc.) — extensibility without modifying the agent.
- **Skills.** Markdown-defined workflows the agent can invoke. Lets advanced users encode domain procedures.
- **Strengths.** Transparent (todo list visible), composable (skills + hooks), scales to large tasks via subagents. The todo+subagent pattern is now a common reference design across the OSS landscape.
- **Limits.** Token-hungry. Each subagent invocation is an additional context window.

## OpenHands (the OSS reference autonomous agent)

OpenHands (formerly OpenDevin) is the open-source community's full-autonomous reference. Largest GitHub project in the category (~75k stars).

- **AgentSkills + microagents.** Modular skill registry with lazy loading.
- **CodeAct.** Encodes actions as executable Python rather than JSON tool calls — increases expressiveness.
- **Sandboxed.** Native sandbox integration via Docker / E2B / Modal / Daytona.
- **Cloud + self-hosted.** All Hands AI sells the managed version.
- **Strengths.** The most research-papered harness; benchmark numbers competitive with closed agents.
- **Limits.** Operational complexity; less polished UX than commercial offerings.

## Goose (extensibility-first)

Goose (Block, now Linux Foundation) treats MCP as the integration substrate from day one.

- **Extension-first.** Every capability is an MCP extension. The core is minimal.
- **Multi-LLM.** Model-agnostic by design.
- **CLI + desktop app.** Same agent, two surfaces.
- **Recipe system.** Reusable task templates.
- **Strengths.** Heaviest investment in MCP ecosystem leverage.
- **Limits.** Harness is leaner than Claude Code or OpenHands; performs best with strong models on well-specified tasks.

## What separates good harnesses

1. **Edit-format reliability.** Bad diff formats waste retries.
2. **Termination logic.** Knowing when to stop is harder than starting.
3. **Error visibility.** Surfacing tool failures cleanly to the model and the user.
4. **Cost discipline.** Subagents and long contexts blow up bills; budget enforcement matters.
5. **Approval UX.** The right level of human-in-the-loop for the task class.
6. **Long-context use.** With 1M+ token models, harnesses that use it well (Claude Code's primitive navigation) outperform those that fight against it.

## The harness convergence (mid-2026)

Patterns that started in one harness now appear in most:
- Todo lists (Claude Code → Cline, OpenHands, Goose, Codex CLI).
- Subagents (Claude Code → Cline, Codex CLI).
- Plan/Act (Cline → Cursor's Plan mode).
- MCP everywhere.
- Git-native edits (Aider → all).
- Sandbox-aware execution (Devin → most async products).

The harness layer is converging. The remaining differentiation is in how each vendor tunes their harness for their preferred surface (CLI vs IDE), preferred model, and target user (power dev vs autonomous task assignment).

## See Also
- [[Model Context Protocol (MCP)]]
- [[Codebase Indexing]]
- [[Cloud Sandboxes]]
- [[Code Execution Environments]]
- [[Competitive Dynamics]]
