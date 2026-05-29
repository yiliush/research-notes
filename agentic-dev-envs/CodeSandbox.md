---
tags: [infrastructure, sandbox, codesandbox, together-ai, ade-cluster]
created: 2026-05-28
---

# CodeSandbox

CodeSandbox started in 2017 as one of the original browser-based IDEs for frontend developers and pivoted, post-acquisition by Together AI in December 2024, into a sandbox-as-a-service for AI agents. The consumer IDE is still there; the strategic product is now the **CodeSandbox SDK** — a microVM execution layer feeding Together AI's Together Code Interpreter, plus standalone agent customers.

## Company / Origin
- Founded 2017 by Ives van Hoorne (Amsterdam). Famous in the React community as the easiest way to share a runnable code example.
- By 2023 CodeSandbox had ~4.5M monthly developers and had developed proprietary microVM tech for fast-resuming dev environments — the basis of the "Devboxes" product.
- **Acquired by Together AI on Dec 12, 2024** for undisclosed terms. Acquisition rationale: Together needed a code-interpreter component for its inference platform, and CodeSandbox's microVM fleet was ready-made.
- Note for the vault: this is *not* a Vercel acquisition. Vercel runs its own competing product, Vercel Sandbox (codename Hive, also Firecracker-based, GA'd in 2025), which powers [[v0]]. The two are commonly confused.

## Funding & Adoption
- Pre-acquisition: ~$15M raised across seed and Series A from EQT Ventures, Kleiner Perkins, and others.
- Together AI acquisition undisclosed; Together itself raised a $305M Series B in Feb 2025 and is widely reported at unicorn+ valuation.
- Customer base post-acquisition: the consumer IDE retains its developer audience; the SDK serves Together Code Interpreter and a growing set of agent vendors that want a snapshot/fork-friendly microVM with strong browser preview integration.

## Architecture
- **Firecracker microVMs** with proprietary snapshotting. The team published research on "memory snapshot resumption" — a sandbox can resume from a paused state in ~1–2 seconds with full memory state intact.
- The standout primitives:
  - **Hibernate / resume.** A VM can be paused mid-execution, its full memory snapshotted, and resumed later with the process tree intact.
  - **Fork.** Snapshots can be cloned to spawn divergent execution branches — the speculative-execution pattern.
  - **Browser preview API.** A first-class iframe-embedding API for showing the running app inside the agent UI, with code injection for hot-reload.
  - **Multi-user sessions.** Multiple humans (or agents) can attach to the same sandbox concurrently.
- SDK exposes built-in JS and Python interpreters, persistent terminals (xterm.js), filesystem-change watchers, and the preview API.

## Pricing
- CodeSandbox SDK: **$0.01486 per VM credit**, where a credit ≈ a VM-hour at a baseline spec; larger VMs consume credits faster.
- VM concurrency tier-gated: each plan has a concurrent-sandbox cap.
- Billed in 1-minute increments (rounded up).
- Consumer IDE has separate Free / Pro / Team tiers, largely unchanged from pre-acquisition.

## Strategic Position
- Now positioned as the agent-execution layer for Together AI's inference platform — the "code-interpreter for any open model" play. Customers using Together for Llama / DeepSeek / Qwen inference get CodeSandbox sandboxes as a single SDK call.
- Differentiators: the snapshot/fork story is more mature than E2B's, and the browser-preview tooling is best-in-class — important for any agent that needs to show the user the running app (vibe-coding, design-to-code).
- Disadvantage vs E2B: less standalone brand among agent builders, since the Together acquisition routed go-to-market through Together's pipeline.
- Competition: [[E2B]], [[Daytona]], [[Modal Sandboxes]], Vercel Sandbox (Firecracker-based, but bundled into Vercel plans for [[v0]]).

## See Also
- [[Cloud Sandboxes]]
- [[E2B]]
- [[Daytona]]
- [[Modal Sandboxes]]
- [[StackBlitz WebContainers]] — alternative browser-IDE heritage
- [[v0]] — uses Vercel Sandbox, not CodeSandbox
- [[Code Execution Environments]]
