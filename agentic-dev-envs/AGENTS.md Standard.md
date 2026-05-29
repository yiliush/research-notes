---
tags: [standard, agents-md, open-format, linux-foundation, ade-cluster]
created: 2026-05-28
---

# AGENTS.md Standard

AGENTS.md is the emerging open standard for project-level agent context files — a plain-Markdown document at the repository root that tells AI coding agents the build commands, test commands, conventions, and boundaries they need to work in the codebase. It is functionally a README for agents: the operational instructions that don't belong in a human-facing README but that every agent needs in order to be useful. Adopted by 60,000+ repositories within nine months of release, now stewarded by the Linux Foundation.

## Origin and Timeline

- **August 2025**: OpenAI released AGENTS.md as a convention for Codex CLI, with collaborators including [[Amp]], Jules (Google), [[Cursor]], and Factory.ai. The format was deliberately minimal — plain Markdown, no required schema — to maximize adoption.
- **Q4 2025**: Rapid adoption across the coding-agent ecosystem. By the December 2025 Linux Foundation announcement, the file was being read natively by Codex, Cursor, Copilot, Gemini CLI, Aider, Windsurf, Zed, Factory, Jules, and 20+ other tools.
- **December 9, 2025**: AGENTS.md was contributed (alongside [[Model Context Protocol (MCP)]] and Goose) as a founding project of the Agentic AI Foundation under the Linux Foundation, with OpenAI, Anthropic, Block as founding members and Google, Microsoft, AWS, Bloomberg, Cloudflare backing.
- **May 2026**: 60,000+ repositories have AGENTS.md files. The format is the de facto standard for agent context.

## Format

The "spec" is intentionally minimal:
- Plain Markdown
- Lives at the project root (or in subdirectories — agents walk down the tree)
- No required headings, no required ordering, no schema
- Convention is to use H2 sections for topics like build, test, lint, conventions, security boundaries

Codex extends this with an instruction-chain pattern: starting at the Git root, walk down to the current working directory, reading `AGENTS.override.md` then `AGENTS.md` at each level. Later (deeper) files override earlier ones — closest-to-the-edit wins.

## Adoption (May 2026)

Read natively by:
- **Codex CLI** (originator) · [[Cursor]] · [[GitHub Copilot]] · [[Gemini CLI]] · [[Aider]] · [[Windsurf]] · [[Zed]] · [[Factory.ai Droids]] · [[Jules]]
- [[Amp]], [[OpenHands]], VS Code agent mode, and 20+ smaller tools
- [[Claude Code]] reads CLAUDE.md by default; community convention is to symlink AGENTS.md ↔ CLAUDE.md for cross-tool portability

Notable holdouts as of May 2026: [[Kiro]] uses its own steering-file convention (`.kiro/steering/*.md`) rather than AGENTS.md, though [[GitHub Spec Kit]] integrates with both.

## Why It Matters

- **The portability problem it solves**: before AGENTS.md, every agent had its own context file format (`.cursorrules`, `.cursor/rules`, `CLAUDE.md`, `.aider.conf.yml`, Continue's `config.json`, Copilot's instructions). Switching agents meant rewriting context. AGENTS.md is the lingua franca.
- **The minimal-spec bet**: deliberately not standardizing structure. The hypothesis is that agents are smart enough to parse arbitrary Markdown, so the value is in the convention (where to look) rather than the schema (what to read).
- **Strategic neutrality**: stewardship by the Linux Foundation rather than any vendor was the gating move for adoption by direct competitors. OpenAI's willingness to give up control was the unlock.

## See Also

- [[Spec-Driven Development]] — adjacent movement; specs and AGENTS.md address different layers (intent vs operational context)
- [[GitHub Spec Kit]]
- [[Model Context Protocol (MCP)]] — fellow Linux Foundation AAIF project
- [[Claude Code]] · [[Cursor]] · [[Codex CLI]] · [[Aider]] · [[OpenHands]]
- [[Agent Harness]]
