---
tags: [moc, cluster-index, cli-agent, ade]
created: 2026-05-28
---

# CLI Coding Agents

The category of AI coding agents that runs in your terminal as a first-class surface — not as a side panel inside an IDE, not as a chat tab in a browser, but as a process you launch from a shell prompt that can read, write, and execute against your filesystem and git repo. This cluster is the fastest-moving front in the ADE market and the one where the most consequential architectural choices (hooks, skills, MCP, sandboxing, plan/execute splits) are being established.

## The Unbundling Thesis

For a decade the assumption was that AI coding assistance belonged inside the IDE — Copilot in VS Code, Cody in JetBrains, Cursor as an IDE fork. CLI agents reject that framing. The argument:

1. **Agents need filesystem and shell, not editor APIs.** Once an agent can run tests, install dependencies, and grep the codebase, the editor becomes optional scaffolding. The terminal is the lowest-common-denominator interface to all of those.
2. **Editor-resident agents are constrained by their host.** Cursor can't easily run a 30-minute refactoring loop while you keep coding. A CLI agent can run headlessly in tmux, in CI, on a remote box.
3. **Models are getting good enough that you don't need to watch every keystroke.** When the agent succeeds on the first try, IDE chrome (inline suggestions, ghost text) is overhead. A CLI prompt + plan + execute loop is leaner.
4. **The terminal is portable.** Same binary, same workflow on laptop, dev container, SSH session, CI runner. IDE extensions don't travel that way.
5. **Sourcegraph replacing Cody (an IDE assistant) with Amp (a CLI-first agent) is the strongest market signal** that even IDE-heritage vendors now believe the agent surface is leaving the editor.

The CLI agent isn't the only ADE form factor — IDE-native (Cursor, Windsurf), web-hosted (Devin, OpenAI's Codex Cloud), and headless background agents all coexist. But the CLI is the form factor where the *architecture* gets defined first: MCP, hooks, skills, sandboxing, and plan mode all debuted in CLI agents before showing up elsewhere.

## Entities in this Cluster

- [[Claude Code]] — Anthropic. Source-available, $1B+ ARR, richest extension surface. The category's center of gravity.
- [[Codex CLI]] — OpenAI. Apache 2.0, Rust, OS-level sandboxing. ~86.6K stars.
- [[Aider]] — Paul Gauthier. Apache 2.0, Python, indie. **Invented diff-based editing**; ~45.5K stars, 6.8M+ pip installs.
- [[Goose]] — Block (now Linux Foundation AAIF). Apache 2.0, Rust core. Desktop + CLI; MCP-first framework.
- [[Amp]] — Sourcegraph spinout under Quinn Slack. Closed source. Replaced Cody; experimented with ad-supported pricing.
- [[Crush]] — Charmbracelet. MIT, Go. LSP-aware, widest OS support, mid-session model swap.
- [[Gemini CLI]] — Google. Apache 2.0, TypeScript. Most stars (~105K), most generous free tier, **sunsetting individuals June 2026** in favor of Antigravity CLI.
- [[Warp]] — Zach Lloyd / Warp Inc. Closed source Rust terminal with Agent Mode. Coined "Agentic Development Environment."

## Shared Architectural Vocabulary

Concepts that emerged inside this cluster and now define the category:

- **MCP (Model Context Protocol)** — Anthropic-authored, adopted by every entry here. The standardization layer that lets one tool's plugins work in another.
- **Hooks** — deterministic shell scripts on lifecycle events (formalized by Claude Code).
- **Skills / Recipes / Extensions** — reusable instruction bundles (Claude Code skills, Goose recipes, Crush via MCP).
- **Plan mode / Architect mode** — planner/executor split (Aider invented "architect", Claude Code formalized "plan mode").
- **Subagents** — isolated-context delegation (Claude Code).
- **Diff-based edits** — Aider's `udiff` format and its descendants.
- **Repo map** — tree-sitter-ranked symbol graphs (Aider, then everyone).
- **OS sandboxing** — Seatbelt/Landlock integration (Codex CLI is the only one going this deep).

## Cluster Dynamics (May 2026)

- **Two open-source giants** (Gemini CLI ~105K stars, Codex CLI ~86.6K stars) — both from frontier labs.
- **One source-available revenue monster** (Claude Code, $1–2B ARR, ~121K stars on its public repo).
- **One indie holdout** (Aider, 45.5K stars, solo dev, pip-installable).
- **One framework play** (Goose, now under Linux Foundation).
- **One enterprise spinout** (Amp, ad-supported then paywalled).
- **One terminal-as-moat play** (Warp, closed Rust terminal).
- **One craft play** (Crush, MIT Go, prettiest TUI).

## See Also
- [[Agentic Development Environments]] (parent category)
- IDE-native ADEs: Cursor, Windsurf, Cline (separate cluster)
- Web/hosted ADEs: Devin, OpenAI Codex Cloud (separate cluster)
