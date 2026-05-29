---
tags: [tool, parallel-orchestrator, python, oss, mit, tmux, hobby-project]
created: 2026-05-28
---

# Agent Farm

The hobby-project end of the parallel-orchestrator spectrum, and the one that pushes the agent count highest. While [[Conductor]] and [[Claude Squad]] target running a handful of agents you actively supervise, Agent Farm is designed to point 20–50 [[Claude Code]] instances at a codebase and let them grind through bug-fixing and best-practices sweeps with lock-based coordination.

## Origin
- Repo: `Dicklesworthstone/claude_code_agent_farm`.
- Author: **Jeffrey Emanuel** ("Dicklesworthstone"), an independent developer with a track record of solo-built AI tooling.
- License: **MIT + OpenAI/Anthropic Rider** (unusual — explicitly defers to underlying TOS).
- Primary language: Python 3.13.
- Released 2025; GitHub stars: **~838** as of May 2026.

## Architecture
- Python orchestrator script that spawns up to 50 Claude Code processes inside a tmux grid.
- **Lock-based coordination**: prevents multiple agents from editing the same file simultaneously by acquiring file-level locks before each tool call.
- Real-time dashboard inside tmux showing per-agent context-window usage, heartbeat, and current task.
- Built-in workflows:
  - **Bug-fixing sweep** — agents pick from a generated bug list, claim a bug, fix it, mark done.
  - **Best-practices sweep** — agents apply a stack-specific best-practices checklist.
  - **Cooperating agents** — coordination implemented entirely through LLM prompts rather than hard-coded logic.
- Stack-aware: ships best-practice guides for 34 technology stacks (Next.js, Python, Rust, Go, Java, Angular, Flutter, C++, etc.).
- Uses `tmux` for terminal multiplexing and `uv` as the Python package manager.

## Distribution & Adoption
- Install: clone the repo and run via `uv`.
- No published binaries, no Homebrew package — pure GitHub-clone-and-run.
- GitHub stars: ~838 as of May 2026; 48 commits on main.

## Pricing
- Free, OSS. The cost model is purely the underlying Claude API spend, which at 20–50 parallel agents becomes the dominant cost — meaningful spend for serious use.

## Differentiators
- **Scale**: targets 20–50 agents, an order of magnitude more than the GUI-based competitors who assume a human triages each diff.
- **Workflow-first**: ships opinionated sweeps (bug-fix, best-practices) rather than a generic "run N agents" UI.
- **Lock-based coordination** instead of git-worktree isolation alone — agents share the same checkout but coordinate file access. This is the architectural contrast with Claude Squad/uzi/Conductor, all of which isolate via worktrees.
- Closest in spirit to a "build farm" or CI sweep than to a developer-paired tool.

## See Also
- [[Parallel Agent Orchestrators]] — cluster index
- [[Claude Squad]] — worktree-isolated alternative
- [[uzi]] — Go equivalent at smaller scale
- [[Claude Code]]
