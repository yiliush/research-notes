---
tags: [market]
created: 2026-05-28
---

# Market Structure and Value Chain

The ADE market segments into six functional zones. Each zone has different unit economics, distribution channels, and defensibility profiles. Most large vendors now span 2-3 zones; the boundaries blur as the category matures.

## Zone 1: Full-IDE (fork-the-editor)

Vendors who ship their own editor — usually a VSCode fork — and own the entire surface from autocomplete to multi-file agent.

- **Cursor (Anysphere)** — VSCode fork. $2B ARR, $50B valuation. Owns indexing (Merkle-tree based), inline edits, agent mode, tab completion model.
- **Windsurf (Cognition, post-acquisition)** — VSCode fork. Cascade agent flow, Riptide/SWE-1 model lineage. ~$82M ARR at acquisition.
- **Zed** — Native Rust editor. Collaborative-first; integrated agent panel; smaller share.
- **JetBrains AI Assistant** — Bundled in IntelliJ/PyCharm/etc. Enterprise distribution via existing license base.

Defensibility: switching costs are real (muscle memory, settings, extensions). Risk: model commoditization makes the editor itself the moat.

## Zone 2: CLI / terminal agent

Run in the shell, edit files, execute commands. Asynchronous-friendly, scriptable, often headless.

- **Claude Code** (Anthropic) — todo-list + subagent loop, ships with Anthropic plans.
- **Codex CLI** (OpenAI) — GPT-5.5-trained, supports parallel subagents.
- **Gemini CLI** (Google) — Open-source, transitioning to Antigravity CLI Jun 2026.
- **Aider** — Diff-based, git-native, model-agnostic.
- **Goose** (Block / Linux Foundation) — MCP-first, multi-LLM.
- **Cline CLI** — Plan/Act paradigm, multi-agent kanban.
- **Jules Tools** (Google) — CLI wrapper for async Jules agent.

## Zone 3: VSCode extension

Live inside the editor the developer already runs. No editor switch required.

- **GitHub Copilot** — incumbent, 20M+ users, native to VS Code and Visual Studio.
- **Cline** — 62k stars; full agent inside VS Code.
- **Continue** — 33k stars; framework for custom agents.
- **Cody (Sourcegraph)** — code-search-anchored context.
- **Augment Code** — context engine specialized for large monorepos.
- **Tabnine, Codeium (residual)** — older autocomplete-first lineage.

## Zone 4: Async / autonomous

Agents that run on managed infrastructure, take a task spec (often a GitHub issue), and return a PR. Developer is reviewer, not pair-programmer.

- **Devin (Cognition)** — first commercial async agent, ACU-billed.
- **Jules (Google)** — Gemini 3 Pro-powered, clones repo to GCP VM, opens PR.
- **Codex cloud** (OpenAI) — managed Codex agents, separate from Codex CLI.
- **OpenHands cloud** — managed All Hands version.
- **Factory** — workflow-defined agents for SDLC slices.

## Zone 5: Vibe-coding / no-code-adjacent

Sells outcomes (running apps) to non-engineers or product builders. Pricing is per-app/credit, not per-seat.

- **Lovable** — $400M ARR, 8M users. Prompt → deployed React app.
- **v0 (Vercel)** — ~$40M ARR. Component/UI generation, now full-stack.
- **Bolt.new (StackBlitz)** — WebContainer-based, instant preview.
- **Replit Agent** — Agent 4 (March 2026 web, May 2026 iPhone). Consumption pricing.
- **Cognition's residual Windsurf brand** — pulling toward this zone via prompt-to-product.

## Zone 6: Specialty SDLC slice

Vendors who own one stage of the software lifecycle deeply rather than the full IDE.

- **Code review:** Greptile, Qodo, CodeRabbit, Graphite Diamond.
- **Test generation:** Diffblue, Qodo, Meticulous.
- **PR triage / issue:** Sweep, Mentat.
- **Codebase Q&A:** Greptile, Sourcegraph Cody.
- **Migration / refactor:** Grit, Codemod.
- **Security:** Snyk DeepCode, Semgrep AI.
- **Observability / debugging:** Sentry's AI debugger, Honeycomb's Query Assistant.

## Value Chain

```
Foundation model (Anthropic, OpenAI, Google, DeepSeek, xAI, Qwen)
   ↓
Agent harness (Aider loop, Cline plan/act, Claude Code todo+subagent, Devin planner)
   ↓
Codebase context layer (embeddings, AST, Merkle-tree sync, RAG)
   ↓
Execution sandbox (devcontainer, E2B, Modal, Daytona, GCP VM, WebContainer)
   ↓
Surface (IDE fork, VSCode extension, CLI, web UI, Slack/GitHub)
   ↓
Distribution (seat licenses, marketplace, OSS install)
```

Vendors increasingly compete vertically across this stack. Cursor builds its own completion model (Composer); Cognition trained SWE-1; Poolside trains a proprietary base model. Owning the model layer is the new front in defensibility for the largest players.

## See Also
- [[Market Landscape]]
- [[Agent Harness]]
- [[Codebase Indexing]]
- [[Cloud Sandboxes]]
- [[Pricing Models]]
