---
tags: [concept, harness]
created: 2026-05-28
---

# Background Agents

Coding agents that run **off the developer's main thread** — in a separate process, container, cloud sandbox, or repository. Distinct from foreground agents (Cursor's Composer, Claude Code's interactive loop) because they don't block the developer's attention while they work. Background agents are how vendors operationalize [[Long-Horizon Coding]] without making the user stare at a spinner for an hour.

## The Three Variants

**1. Local background tasks** — agent works in a separate process on your machine, often in a git worktree, while you continue working on the main branch. [[Conductor]], [[Claude Squad]], and [[Container Use]] are the orchestration layer for this pattern. Cursor's Background Agents feature is the integrated version.

**2. Cloud sandboxed agents** — agent runs in a vendor's managed sandbox ([[E2B]], [[Modal Sandboxes]], [[Daytona]], custom Firecracker VMs). [[Devin]], [[Jules]], [[Codex Cloud]], [[OpenHands]] cloud all use this model. Developer triggers the task and reviews results later via web UI, PR, or Slack.

**3. Event-triggered agents** — agent fires on a repository or organizational event (PR opened, issue labeled, alert fires). [[CodeRabbit]], [[Greptile]], [[Resolve.ai]] (on-call), [[GitHub Copilot]] coding agent (on @-mention in issues) all fit. The agent is plumbed into the SDLC rather than the editor.

## What All Three Share

- **No live human attention** during execution.
- **A callback surface** — PR, Slack message, web UI status — that pulls the human in when the work is done (or stuck).
- **A sandbox or isolation layer** — without it, parallel background work corrupts the developer's working tree.

## Why They Exist

Two reasons:
1. **Parallelism** — one developer can have 5 agents running 5 different tasks in parallel. The only constraint is review bandwidth.
2. **Long horizons** — a task that takes 90 minutes shouldn't block 90 minutes of developer flow. Background pushes the latency cost off the user's critical path.

## The Review Bottleneck

The hard problem isn't running the agent in the background — it's the **human review surface**. When 5 background agents each return a 40-file diff, the developer has to context-switch into each of them. Conductor, Crystal (before deprecation), and Claude Squad differentiate primarily on review UX, not on the agents themselves. PR-based async agents (Devin, Jules) inherit GitHub's review primitives, which is both their strength (familiar) and weakness (not designed for AI-volume diffs).

## Open Problems

- **Notification overload** — 5 agents finishing at random produce 5 attention demands.
- **Conflict resolution** — multiple background agents touching overlapping files in parallel.
- **Cost transparency** — long-running agents burn tokens out of sight; users only see the bill.
- **Failure modes** — agent gets stuck mid-task and silently spins for an hour before timing out.
- **Trust calibration** — without watching the agent work, developers can't form intuition for when to trust the output.

## See Also
- [[Long-Horizon Coding]]
- [[Autonomous Coding Agents]]
- [[Parallel Agent Orchestrators]]
- [[Cloud Sandboxes]]
- [[Inner Loop vs Outer Loop]]
