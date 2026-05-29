---
tags: [concept, infrastructure]
created: 2026-05-28
---

# Model Context Protocol (MCP)

Anthropic launched the Model Context Protocol in November 2024 as an open standard for connecting LLM applications to external tools, data, and resources. By mid-2026 MCP is the de facto integration protocol for coding agents — every major IDE/CLI agent supports it, every frontier-model lab supports it, and the public MCP server registry has grown to ~9,400 listed servers (with one independent census counting 17,468 across all registries). 78% of enterprise AI teams report at least one MCP-backed agent in production (DigitalApplied census, April 2026). The protocol changed how tool-calling for coding agents works: instead of every vendor hand-wiring every integration, vendors expose tools as MCP servers and agents consume them via a stable wire protocol.

## What it is, technically

MCP defines:
- **Servers** — processes that expose tools, resources, and prompts to LLM clients.
- **Clients** — LLM applications that connect to servers and call their tools.
- **Transport** — stdio for local, HTTP + Server-Sent Events for remote, and a streamable HTTP variant.
- **Capabilities** — tool listing, resource reading, prompt templates, sampling (server-initiated LLM calls), logging.
- **Authentication** — OAuth 2.1 layered on remote transports; enterprise IdP integration is a 2026 roadmap priority.

The wire format is JSON-RPC 2.0. The server vocabulary is small: `tools/list`, `tools/call`, `resources/list`, `resources/read`, `prompts/list`, `prompts/get`. Versioning is via protocol version negotiation at handshake.

## Why it reshaped coding agents

Before MCP, every agent vendor wrote a bespoke integration for every external system: a GitHub tool, a Jira tool, a Postgres tool, a filesystem tool, a browser tool. The same Postgres integration got reimplemented in Cursor, Cline, Aider, Continue, OpenHands, and Goose.

MCP collapsed this into one server, many clients. A vendor (Postgres, GitHub, AWS, Stripe, internal enterprise team) writes one MCP server; every agent harness that speaks MCP can use it. This unlocked:
- **A long tail of integrations** for niche tools that would never have justified bespoke per-agent work.
- **Enterprise-internal MCP servers** wrapping legacy systems — exposed to all approved agent surfaces at once.
- **Cross-vendor agent portability** — a Claude Code workflow built against an MCP server runs against Codex CLI or Cline with the same server.

## Adoption (verified May 2026)

**Clients with MCP support:**
- Claude Desktop and Claude Code (native, Anthropic-first)
- ChatGPT (Apps SDK + Connectors, since April 2025)
- Cursor, Windsurf (Cognition), Zed, JetBrains AI Assistant
- Google Gemini API and Vertex AI Agent Builder (added March 2026)
- Cline, Aider, Continue, Goose, OpenHands (open-source)
- Vercel AI SDK, OpenAI Agents SDK
- Microsoft Copilot Studio agents

Effectively every major LLM client supports MCP by mid-2026. 67% of CTOs name MCP as their default agent-integration standard. Competing protocols (Google's A2A, IBM's ACP, UCP) trail at 23%, 8%, 4% respectively.

**Server ecosystem.**
- Public MCP server registry: ~9,400 servers (Q1 2026, +18% MoM).
- Independent Nerq census: ~17,468 indexed across registries.
- ~97M monthly downloads of MCP-related packages.
- Quality is uneven — only ~12.9% score "high trust" (≥70/100) for documentation and maintenance.

**Anchor servers** (the canonical reference implementations):
- Filesystem, Git, GitHub, GitLab
- Postgres, SQLite, Memory
- Slack, Linear, Notion, Jira
- Puppeteer / browser (for web automation)
- AWS, GCP, Azure (cloud control planes)
- Sentry, Datadog, PagerDuty (observability)

## 2026 Roadmap Priorities

From the official MCP roadmap (modelcontextprotocol.io blog, Q1 2026):

1. **Enterprise authentication.** OAuth 2.1 hardening, enterprise IdP federation, fine-grained scope management. Largest single blocker to wide enterprise rollout.
2. **Multi-agent coordination.** Agent-to-agent tool calling via MCP. Lets an orchestrator agent treat sub-agents as MCP servers.
3. **Curated, verified registry.** A first-party MCP registry with security ratings, trust scores, and signed releases. The current decentralized model has produced supply-chain risk (~12.9% high-trust rate is the symptom).
4. **Streaming and long-running tasks.** First-class support for tools that take seconds-to-hours, with progress events.
5. **Discovery and capability negotiation improvements.** Smarter handshakes so clients can avoid loading thousands of unused tools.

## Critique and Open Issues

- **Tool-list bloat.** A power-user MCP setup easily registers 50+ servers, each exposing 5-20 tools. Models waste tokens on irrelevant tool descriptions and choose wrong tools more often. Mitigation: tool filtering, lazy capability fetch, prompt-time tool selection.
- **Auth surface is wide.** Every remote MCP server is another OAuth integration, another set of refresh tokens, another security audit. Enterprises are deploying MCP gateways (a single auth boundary in front of many internal servers).
- **Supply chain.** Unverified servers can exfiltrate code or secrets. The 12.9% high-trust rate matters.
- **Versioning drift.** Anthropic ships protocol changes frequently; client/server version mismatch is a real production issue.

## Why it mattered for coding agents specifically

Coding agents are tool-heavy by nature — they need filesystem, shell, git, package managers, language servers, debuggers, browsers, and increasingly cloud APIs. Before MCP, no shared format meant duplicated work and the "every agent for itself" integration explosion. MCP turned tool-calling into a marketplace, and the agent harness vendors became MCP clients first and integration vendors a distant second. This is the single largest infrastructure shift in the ADE category between 2024 and 2026.

## See Also
- [[Agent Harness]]
- [[Cloud Sandboxes]]
- [[Codebase Indexing]]
- [[Competitive Dynamics]]
