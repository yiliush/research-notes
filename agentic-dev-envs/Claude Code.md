---
tags: [tool, cli-agent, proprietary, source-available, anthropic, flagship]
created: 2026-05-28
---

# Claude Code

Anthropic's terminal-native coding agent and the de facto reference design for the CLI agent category. Shipped as a closed-binary npm package whose source is publicly readable in the `anthropics/claude-code` repo, it bundles hooks, subagents, skills, MCP, plan mode, slash commands, and a plugin marketplace into the most opinionated and extensible CLI agent on the market — and the fastest-growing developer tool product in history by revenue.

## Origin
- Launched as a research preview on **February 24, 2025** alongside Claude 3.7 Sonnet; general availability in **May 2025** with Claude 4.
- Built by Anthropic. Authored primarily in TypeScript (the leaked 512K-line source map in April 2026 confirmed this).
- Latest npm version on the trunk as of May 2026: `@anthropic-ai/claude-code` 2.1.152.

## Architecture
- **Model support:** Anthropic Claude (Opus, Sonnet, Haiku families). Plan mode commonly pairs Opus (planner) with Sonnet (executor).
- **Harness primitives:**
  - **Hooks** — deterministic shell scripts wired to lifecycle events (PreToolUse, PostToolUse, SessionStart, etc.). Cannot hallucinate; intended for security checks, formatters, linters.
  - **Subagents** — specialized agents with isolated context windows; only summaries return to the parent thread.
  - **Skills** — reusable instruction bundles with frontmatter, supporting files, and dynamic context. Anthropic's preferred extension shape.
  - **Slash commands** — user-defined and built-in (`/plan`, `/clear`, `/compact`, etc.).
  - **Plan mode** — read-only planning phase that requires user approval before execution.
  - **CLAUDE.md** — advisory project memory (vs. mandatory hooks).
- **MCP:** First-class client. Anthropic invented the protocol; Claude Code was its earliest non-trivial consumer.
- **Sandboxing:** Per-tool permission prompts, configurable allow/deny lists in `settings.json`, optional containerized sandbox mode.
- **Plugin ecosystem:** Plugin marketplace with curated and community plugins; `awesome-claude-code-and-skills` registry indexes hundreds.

## Distribution & Adoption
- License: proprietary binary, source-available in `anthropics/claude-code` (not OSI-licensed but inspectable and PR-accepting).
- Install: `npm install -g @anthropic-ai/claude-code` (per-platform optional dependencies pull a native binary), Homebrew, native installer.
- GitHub stars: **~121K** as of late April 2026 (up from 81.6K early 2026 — climbed ~40K in ~3 months).
- npm: ~8.2M cumulative downloads on `@anthropic-ai/claude-code`.
- Revenue: hit **$1B ARR by November 2025** (~6 months post-GA); estimated near $2B ARR by January 2026 — faster ramp than ChatGPT.

## Pricing
- Bundled with Claude Pro ($20/mo) and Claude Max ($100/mo, $200/mo).
- API pay-as-you-go also supported (bring your own Anthropic API key).
- Brief April 2026 attempt to gate Claude Code behind Max-only was reversed within hours after backlash.

## Differentiators
- The richest extension surface in the cluster: hooks + skills + subagents + MCP + plan mode + plugins.
- Source-available but commercially controlled — unique middle path vs. Aider/Codex (fully OSS) and Warp/Amp (closed).
- Anthropic's MCP makes Claude Code the canonical reference implementation; every other tool here implements MCP to interop with the same servers Claude Code uses.
- Plan mode + subagents enable a planner/executor split that other CLIs approximate but don't formalize.
- Revenue trajectory shows the category isn't a hobbyist niche — it's a primary developer surface.

## See Also
- [[CLI Coding Agents]]
- [[Codex CLI]]
- [[Amp]]
- [[Aider]]
