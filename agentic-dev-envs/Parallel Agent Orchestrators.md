# Parallel Agent Orchestrators

The thin layer that sits one rung above [[Claude Code]] / [[Codex CLI]] and lets a single developer drive N coding agents at once — each in its own git worktree, each on its own branch, each reviewable as an independent diff. This cluster did not exist in early 2025. By mid-2026 it is the most active build-out in the ADE landscape, populated by a mix of YC-backed Mac apps, terminal TUIs, and bash farms.

## Why this exists

A single Claude Code session occupies one repo, one branch, and (usually) one developer's attention. The moment agents got reliable enough to leave running unattended — roughly the post-Claude-4 inflection in mid-2025 — the bottleneck shifted from agent quality to **how many simultaneous threads of work one human could supervise**. Git worktrees turned out to be the right primitive: cheap to create, fully isolated on disk, mergeable through normal review flows. The orchestration pattern that emerged is identical across nearly every tool in this cluster:

1. Spawn N worktrees from a base branch

2. Launch one agent (typically Claude Code) per worktree, often inside a tmux session or container

3. Surface progress, diffs, and prompts in a single pane (TUI, desktop GUI, or web)

4. Let the human approve, merge, or discard each branch

That is the whole category. The differentiation lives in distribution shape (Mac app vs. terminal vs. bash script), isolation strength (worktree vs. container), and the UX of triaging N parallel diffs.

## Who's building here

Two distinct populations, with little overlap in distribution strategy:

**YC / VC-backed product companies** — building polished Mac or web GUIs, raising rounds, charging (or planning to charge) teams.

* [[Conductor]] — Melty Labs, YC S24, $22M Series A (Spark + Matrix), Mac-native

* [[Crystal]] — Stravu, MIT-licensed Electron app; deprecated Feb 2026 in favor of Nimbalyst

**OSS hobby / dev-tool projects** — terminal-first, git-worktree-pure, distributed via Homebrew or `go install`.

* [[Claude Squad]] — smtg-ai, ~7.7K stars, AGPL-3.0, tmux-based TUI in Go

* [[uzi]] — devflowinc (the Trieve team), ~579 stars, MIT, Go CLI

* [[Container Use]] — Dagger, ~3.8K stars, Apache-2.0 — containers instead of worktrees

* [[Agent Farm]] — Dicklesworthstone, ~838 stars, MIT, Python bash-style orchestrator for 20–50 agents

* [[VibeKit]] — Superagent Technologies, ~1.8K stars, MIT — sandbox layer, parallelism is secondary

* [[Backlog.md]] — MrLesk, ~5.6K stars, MIT — task-queue feeding agents, not an orchestrator per se but increasingly used as one

## Relationship to single-agent CLIs

This cluster is unambiguously a **layer above** [[Claude Code]], [[Codex CLI]], [[Aider]], and friends. None of these tools ship their own model or their own agent loop — they spawn existing CLI agents as subprocesses. The implications:

* **Model economics flow through the underlying CLI** — Conductor and Claude Squad bill nothing for inference; the user's Claude Max subscription or API key does.

* **Capability ceiling tracks the host agent** — when Claude Code adds plan mode or skills, the orchestrators inherit them for free.

* **The defensible surface is human-side UX**: how fast can you triage 8 in-flight diffs, switch between them, kill the bad ones, merge the good ones. Not model quality.

This is also why Anthropic's own April 2026 ship of native worktree support in Claude Code (`/worktree`) compressed but did not erase the category — the official feature gives you parallel sessions, but no unified review pane across them.

## Adjacent / blurred-edge entries

* [[Cursor]] 2.0's multi-agent mode (Oct 2025) is a parallel orchestrator embedded in an IDE rather than a standalone tool — same primitive, different distribution.

* [[Codex Cloud]] runs parallel agents server-side instead of locally — a different shape of the same problem.

* [[Container Use]] sits on the edge: it's a sandboxing layer first, parallel-agent enabler second.

## See Also

* [[Conductor]]

* [[Claude Squad]]

* [[Crystal]]

* [[uzi]]

* [[Container Use]]

* [[Agent Farm]]

* [[VibeKit]]

* [[Backlog.md]]

* [[Claude Code]] — the agent these mostly orchestrate

* [[Codex CLI]]

* [[CLI Coding Agents]]

* [[Market Landscape]]

⠀