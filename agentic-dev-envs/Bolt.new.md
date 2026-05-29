---
tags: [vibe-coding, browser-based, prompt-to-app, stackblitz, webcontainers, ade]
created: 2026-05-28
---

# Bolt.new

Bolt.new is StackBlitz's browser-based prompt-to-app builder. You type what
you want, an LLM (Claude by default) writes a full-stack app, the app runs
inside a WebContainer in your browser tab, and you deploy to Netlify with
one click. It is the platform that proved the category could be profitable.

## Origin

StackBlitz had spent years building WebContainers — a Node.js runtime that
runs in the browser via WebAssembly. Bolt.new, launched in October 2024,
was the bet that this runtime, plus a coding LLM, could replace a local dev
environment for the kind of project a non-engineer wants to ship. CEO Eric
Simons positioned it as "the entire IDE moves into the chat."

## Funding & Traction

- StackBlitz total raised: $135M
- Series B: January 2025, led by Emergence Capital and GV
- ARR: $0 to $40M in ~5 months through mid-March 2025; company reported
  profitable
- Users: 5M registered within first year
- May 2026: announced Microsoft Azure and Microsoft 365 partnership, adding
  Microsoft Marketplace as a procurement channel alongside AWS Marketplace

## Product

You start with a chat prompt or a starter template. The agent generates a
full project — React, Next.js, Astro, Svelte, or vanilla — running live in
a WebContainer preview without leaving the tab. Code is fully editable in
a VS Code-style file tree. Errors caught by the runtime are fed back into
the chat automatically.

**Generated stack**: Modern JS frameworks (React, Next.js, Astro, Vue,
Svelte). Supabase is the default for auth and database. Stripe for payments.
Expo for mobile.

**Deployment**: One-click to Netlify (default), Vercel, or Cloudflare.
Bolt-hosted preview URLs are free.

**Models**: Claude (4.6 as of May 2026) is the default. The open-source
fork `bolt.diy` exposes any LLM, but the hosted Bolt.new is Claude-first.

Bolt v2, shipped October 2025, marked the explicit pivot from "experimental
vibe coding" toward enterprise-grade production work, adding team templates,
editable Netlify URLs and pluggable model selection.

## Pricing (May 2026)

| Tier | Price | Token allowance |
|------|-------|------------------|
| Free | $0 | 1M tokens/mo, 300K daily cap |
| Pro | $25/mo | 10M tokens/mo |
| Teams | $30/user/mo | pooled, plus collaboration |
| Enterprise | $100K base on AWS Marketplace | $150/seat, $0.01/extra token, 12-month contract |

Unused tokens roll over for one additional month on paid plans.

## Differentiators

- **WebContainers.** Bolt is the only major platform that runs the generated
  app's actual Node.js process in the user's browser. No remote sandbox.
  This makes the feedback loop noticeably faster than v0 or Lovable.
- **Open stack.** Bolt does not lock users to a deployment target. v0 pulls
  toward Vercel, Lovable toward Supabase. Bolt lets you take the code and
  go anywhere.
- **bolt.diy** exists as an open-source variant — defuses some "what if
  StackBlitz dies" hesitation among indie users.
- **Enterprise procurement.** AWS and Azure Marketplace listings are
  unusual for the category and reflect serious sales motion.

## See Also

- [[Vibe Coding Platforms]]
- [[Vibe Coding]]
- [[v0]]
- [[Lovable]]
- [[Replit Agent]]
