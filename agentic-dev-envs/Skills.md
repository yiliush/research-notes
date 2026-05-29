---
tags: [concept, primitive, harness]
created: 2026-05-28
---

# Skills

A primitive where a coding agent loads a self-describing capability bundle — instructions, scripts, examples — on demand, only when the user's task seems to call for it. Skills are a lighter-weight cousin of [[Model Context Protocol (MCP)]] tools: instead of running a server, a skill is just a folder of markdown plus optional scripts that the agent reads when relevant. Anthropic's term, now generalizing.

## The Pattern

A skill consists of:
- **A name + description** — the agent uses these to decide whether the skill applies.
- **Instructions** (markdown) — what to do when the skill is invoked, often a step-by-step playbook.
- **Optional scripts / templates / references** — concrete code or files the skill drops in or runs.

The agent's harness keeps a registry of available skills. When the user's prompt seems to match a skill's description, the agent loads that skill's full content into context and follows it.

## Why It Won (in Claude Code)

Three structural advantages:
1. **Just files** — a skill is a markdown folder. Authoring, sharing, version-controlling are trivial. No SDK, no runtime, no server.
2. **Just-in-time loading** — skills don't burn context until they're invoked. Hundreds can be installed; only the relevant one(s) load per task.
3. **Composability with [[Hooks]]** — hooks gate behavior, skills extend behavior; the two compose cleanly.

## Who Ships It

- **[[Claude Code]]** — invented the user-facing "Skill" primitive; installable via plugins, organized in a per-project or per-user library. Most developed skill ecosystem.
- **[[Cursor]]** — `.cursorrules` and the `@` mention catalog serve a related role; not strictly skills but adjacent.
- **[[Codex CLI]]** — `AGENTS.md` and project-level instructions function as ambient skills.
- **[[Aider]]** — conventions live in `CONVENTIONS.md`; closest equivalent.

## Skills vs MCP Servers

| Dimension | Skills | MCP servers |
|---|---|---|
| What | Folder of markdown + scripts | Long-running process exposing tools |
| Runtime | None (read on demand) | Continuous process |
| Best for | Procedures, playbooks, templates | External APIs, state, complex tool logic |
| Distribution | Git, marketplace | Registry (Smithery, mcp.run, Glama) |
| Trust | Reads files in your repo | Talks to network services |

Most agents now ship both. Skills are for things like "how this team writes commits" or "how to deploy this service"; MCP is for "talk to Linear" or "query Postgres."

## Open Problems

- **Skill collision** — multiple skills match a prompt; the agent picks the wrong one.
- **Skill drift** — the playbook in the skill no longer matches the actual codebase.
- **Skill quality control** — community skill libraries have wide quality variance.
- **Skill discoverability for the user** — the user doesn't know what skills the agent has, so doesn't shape prompts around them.

## See Also
- [[Hooks]]
- [[Model Context Protocol (MCP)]]
- [[AGENTS.md Standard]]
- [[Agent Harness]]
- [[Claude Code]]
