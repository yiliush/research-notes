---
tags: [concept, primitive, harness]
created: 2026-05-28
---

# Hooks

A primitive that binds shell commands to lifecycle events in a coding agent — pre-tool-use, post-tool-use, session-start, session-end, prompt-submit. Hooks let the developer (or the team) extend the agent's behavior without touching the agent's source code, the way git hooks extend git. Pioneered as a first-class primitive by [[Claude Code]] and now spreading.

## What They Do

A hook is just a shell command (or script) that the harness invokes on a specific event. Common uses:

- **PreToolUse** — block dangerous commands (delete, force-push) before they run; rewrite the command; require human approval; log for audit.
- **PostToolUse** — run linters/formatters automatically after every file edit; trigger tests; sync state to a tracker.
- **SessionStart** — load project context, set up worktrees, prime environment variables.
- **UserPromptSubmit** — inject project rules, attach relevant docs, redact secrets before the model sees them.
- **Stop** — final verification gate (typecheck, tests, security scan).

## Why They Matter

Hooks turn the agent harness from a closed black box into an **extension point**. A team can encode policy ("never run `rm -rf` without confirmation," "always run `ruff format` after edits") without forking the agent. This is the same insight that made git hooks, webhooks, and CI hooks valuable.

For enterprises, hooks are the answer to "how do we make this agent safe to deploy at scale" — you wrap every tool call in a corporate-policy filter that the agent itself doesn't know exists.

## Who Ships It

- **[[Claude Code]]** — the most developed hooks system; configured via `settings.json`. PreToolUse hooks can block tool calls. Hooks treated as user input, so they can talk back to Claude.
- **[[Codex CLI]]** — has a hooks-like system via its config.
- **[[Aider]]** — `/run` and `--auto-commit` are simpler precursors.
- **[[Goose]]** — extensions system serves a similar role.
- **[[Cline]]** — partial hooks support; less developed.

## The Layering

Hooks compose with other primitives:
- **Hooks + [[Skills]]**: skills define what the agent *can* do; hooks define what the agent *must* check before doing it.
- **Hooks + [[Model Context Protocol (MCP)]]**: MCP gives the agent access to external tools; hooks gate the use of those tools.
- **Hooks + [[Subagents]]**: hooks fire at the parent level; sub-agent behavior can be policed without modifying the sub-agent prompt.

## Open Problems

- **Hook performance** — running a linter on every edit adds latency. Heavy hooks turn a fast agent into a slow one.
- **Hook ordering** — multiple hooks on the same event can fight (formatter A reformats what formatter B just wrote).
- **Hook discoverability** — users don't know what hooks are running unless the harness shows it transparently.
- **Security** — a malicious settings.json can install a hook that exfiltrates code on every prompt. Trust boundary is the same as `.envrc` or git hooks.

## See Also
- [[Agent Harness]]
- [[Skills]]
- [[Model Context Protocol (MCP)]]
- [[Claude Code]]
