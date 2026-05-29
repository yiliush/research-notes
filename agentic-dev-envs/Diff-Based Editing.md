---
tags: [concept, primitive]
created: 2026-05-28
---

# Diff-Based Editing

A pattern where the coding agent emits its changes as **unified diffs** (or a search/replace block) rather than rewriting whole files. Pioneered by [[Aider]] and copied so widely it's now invisible — but it's one of the most consequential design choices in the ADE category, with direct implications for cost, accuracy, and reviewability.

## The Three Editing Strategies

| Strategy | Output | Cost | Accuracy |
|---|---|---|---|
| **Whole-file rewrite** | Agent emits the entire new file | High (file size in tokens) | High but loses formatting |
| **Diff / patch** | Agent emits a unified diff or search/replace block | Low (only the change) | Sensitive to whitespace/context |
| **Tool-call edit** | Agent invokes an `edit` tool with old/new strings | Medium | Highest — enforced exact match |

Most production agents now use the third (tool-call) form because it sidesteps diff parsing fragility, but the *idea* is Aider's diff insight: only the change should be transmitted.

## Why It Won

- **Cost** — for a 5-line change in a 2,000-line file, whole-file output costs ~400x more tokens than a diff.
- **Speed** — fewer output tokens means faster completion.
- **Reviewability** — a diff is the natural review unit (git, PRs, code review).
- **Surgical precision** — the agent has to explicitly identify what's changing, which forces clearer thinking.

## Why It's Hard

- **Whitespace drift** — diffs fail if the agent's understanding of leading whitespace is off by one character.
- **Context anchors** — search/replace needs unique context strings; the agent has to choose them well.
- **Multi-hunk coordination** — a single edit may need 3 hunks in 3 places that have to apply atomically.
- **Apply failures** — when the diff doesn't apply cleanly, the agent has to retry, often blowing up the token budget.

## The Tooling Lineage

- **[[Aider]]** (2023) — invented the modern OSS implementation; multiple edit formats including unified diff and search/replace blocks; auto-commit per edit.
- **[[Cursor]]** — proprietary fast-apply model rewrites diffs into the editor; the "apply model" is a real differentiator.
- **[[Cline]]** — diff-based editing with retry loops.
- **[[Claude Code]]** — `Edit` tool with `old_string`/`new_string` is the tool-call descendant of diff editing.
- **[[Continue]]** — supports diff and tool-call edits depending on model.

## The Apply Model

Cursor's underrated innovation: a small dedicated model whose only job is to apply a poorly-formatted diff to a file correctly. The main agent produces an imprecise diff cheaply; the apply model resolves it. This is essentially a **two-stage edit pipeline** — a pattern other vendors have started copying.

## Open Problems

- **Atomic multi-file edits** — diffs across multiple files have to apply as a unit or roll back together; few harnesses do this well.
- **Conflict with concurrent edits** — the user types while the agent is mid-edit; the diff context becomes stale.
- **Reformat-after-edit interactions** — formatters and linters reflow code, invalidating remembered context for the next edit.
- **Large-file edits** — 10K-line files break naive diff models; the apply pipeline has to chunk.

## See Also
- [[Aider]]
- [[Cursor]]
- [[Agent Harness]]
- [[Codebase Indexing]]
