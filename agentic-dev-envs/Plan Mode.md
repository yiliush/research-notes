---
tags: [concept, primitive, harness]
created: 2026-05-28
---

# Plan Mode

A two-phase loop where the agent first produces a structured plan that the developer reviews, then executes the plan in a separate mode. Pioneered by [[Cline]] as the "Plan / Act" paradigm and now near-ubiquitous across coding agents. It's the most successful answer to the "agent runs off and does the wrong thing for an hour" failure mode that dominated 2024.

## The Pattern

1. Developer states the goal in natural language.
2. Agent enters **plan mode**: reads relevant files, asks clarifying questions, produces a written plan (numbered steps, files-to-touch list, acceptance criteria).
3. Developer reviews and edits the plan. Sometimes iterates.
4. Agent enters **act mode** (or "execute"): runs the plan step by step, often with a per-step approval gate or a single up-front approval.
5. Verification phase: tests run, diffs reviewed, developer accepts or asks for changes.

## Why It Won

The alternative — "give the agent a goal, let it work" — has a punishing failure mode. When an agent makes a wrong inference in step 1, it compounds across 50 tool calls; the developer wastes time on cleanup or rerolling. Plan mode forces the misalignment to surface **before** any code is written.

It also serves a political function: it gives the developer something to **review and approve**, which is essential for enterprise adoption. "Agent did stuff" is illegible; "agent followed this plan" is auditable.

## Who Ships It

- **[[Cline]]** — coined "Plan / Act"; ships as a top-level toggle in the UI.
- **[[Claude Code]]** — `/plan` mode and a planning todo-list primitive baked into the harness.
- **[[Roo Code]]** — inherited from Cline; expanded with "Architect / Code / Debug / Ask" modes.
- **[[Aider]]** — `/architect` mode using a strong model for planning, then a cheap model for execution.
- **[[Cursor]]** — plan-before-execute baked into Composer/Agent.
- **[[Continue]]** — agent modes including planning.
- **[[OpenHands]]** — planner agent that delegates to executor sub-agents.
- **[[Devin]]** — async agents always plan first; the plan is the developer's primary surface.
- **[[Kiro]]** — spec-driven: the spec **is** the plan, written before any code.

## The Variations

- **Two-model plan/act**: cheap fast model for execution; expensive reasoning model for planning. Aider's `--architect` flag is the canonical implementation; many CLIs followed.
- **Plan as todo list**: Claude Code's todos are a structured plan that updates as work progresses, visible to the user.
- **Plan as spec**: Kiro / [[Spec-Driven Development]] elevates the plan to a versioned, durable artifact.
- **Plan as PR description**: outer-loop agents (Devin, Jules) publish the plan in the PR body for review.

## Open Problems

- **Plan staleness** during long execution — when the codebase moves under the agent's feet.
- **Plan-execution divergence** — the agent quietly does something different and the developer doesn't notice.
- **Plan inflation** — over-engineered plans for trivial tasks (the "ChatGPT problem" generalizes).
- **Replanning** — when execution reveals the plan was wrong, the loop has to gracefully restart without losing context.

## See Also
- [[Agent Harness]]
- [[Spec-Driven Development]]
- [[Cline]]
- [[Claude Code]]
- [[Aider]]
- [[Subagents]]
