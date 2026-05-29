---
tags: [vibe-coding, browser-based, prompt-to-app, replit, agent, ade]
created: 2026-05-28
---

# Replit Agent

Replit Agent is the autonomous coding agent built into Replit's browser
IDE. It is Replit's pivot from "online IDE for hobbyists" to "natural-
language platform for shipping production apps." Replit Agent is the
reason Replit's valuation tripled to $9B in six months.

## Origin

Replit started in 2016 as a browser-based REPL and IDE used heavily by
students and hobbyists. Through 2023-2024 it struggled to monetise. In
September 2024 it shipped the first version of Replit Agent as a
chat-driven coding assistant integrated into the existing IDE. Agent 3
shipped in 2025; Agent 4 shipped alongside the March 2026 funding round.
The defining move: Replit went from "IDE that has AI" to "AI that has
an IDE attached."

## Funding & Traction

- ARR: $150M as of September 2025
- ARR target: $1B by end of 2026 (~7x in 15 months)
- March 2026: $400M raise at $9B valuation. Prior $3B valuation six
  months earlier, tripled in that window.
- Notable: launched parallel agent execution with Agent 4

## Product

Replit Agent operates inside Replit's full browser IDE. Unlike Lovable
or Bolt, the file tree, terminal, and package manager are first-class
citizens. The agent works alongside the human, who can take over at any
point.

**Generated stack**: Polyglot. Python, Node, Go, Rust, React, Next.js,
Flask, FastAPI, Express. Replit ships its own managed Postgres, key-value
store, object storage, and deploy targets — apps live end-to-end inside
Replit infrastructure.

**Deployment**: Replit Deployments (autoscale, static, scheduled,
reserved-VM). One-click. Custom domains. Apps can be made public, private,
or team-scoped.

**Effort-based pricing.** Agent 3+ uses effort-based metering: simple
edits cost under $0.25, complex multi-file changes bundle into a single
flat charge. This is the category's clearest move away from raw token
metering — closer to outcome pricing.

**Agent 4 parallelism.** Multiple agents can work on independent
sub-tasks in parallel inside the same workspace.

## Pricing (May 2026)

| Tier | Price | Notes |
|------|-------|-------|
| Free | $0 | limited Agent access, public Repls |
| Core | $25/mo ($20 annual) | monthly Agent credits, private projects |
| Pro | $100/mo (Feb 2026) | up to 15 builders, tiered credit discounts, rollover, priority support |
| Teams | $40/user/mo | shared workspaces, pooled Agent credits |
| Enterprise | custom | SSO, governance, dedicated support |

Pro launched in February 2026 and replaced the prior Teams tier.

## Differentiators

- **Polyglot.** Bolt, Lovable and v0 all push you toward Next.js or
  React + Supabase. Replit Agent will write Python, Rust, or Go. It is
  the only major vibe coding platform comfortable in the backend.
- **The IDE is still there.** A user who outgrows the agent does not
  have to leave the platform. The escape hatch is the same surface, not
  a code export.
- **Hosting included.** Replit owns the runtime, the deploy, and the
  database. Margins do not leak to Vercel or Supabase.
- **Effort-based pricing** is the category's most defensible answer to
  the "tokens are weird billing" problem.
- **Long install base.** Millions of educational users created a top of
  funnel no other vendor in this category has.

## See Also

- [[Vibe Coding Platforms]]
- [[Vibe Coding]]
- [[Bolt.new]]
- [[Lovable]]
- [[v0]]
- [[Databutton]]
