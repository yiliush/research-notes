---
tags: [infrastructure]
created: 2026-05-28
---

# Cloud Sandboxes

Cloud sandboxes are the execution substrate for autonomous coding agents. They are ephemeral Linux environments — usually microVMs or containers — that an agent can spawn programmatically, run arbitrary code in, mount a git repo into, and discard. Without them, every agent has to use the developer's local machine; with them, agents can run massively in parallel, asynchronously, and on managed infrastructure. The category emerged in 2024 around E2B, exploded in 2025 with Modal Sandboxes and Daytona joining, and is now a foundational layer beneath every async coding agent shipped in 2026.

## Why agents need them

Three pressures combined:
1. **Untrusted code execution.** Agents write code that should not run on user laptops or production servers. A sandbox provides isolation.
2. **Parallel agent runs.** Cognition Devin, Jules, Codex cloud, Cursor Agents, OpenHands all run dozens to hundreds of agent instances simultaneously per organization. Each needs its own environment.
3. **Reproducibility and disposability.** Agents need a clean state — fresh git clone, fresh dependencies, fresh process tree. Microsecond-to-second boot times make this economical.

## The Major Providers (mid-2026)

| Provider | Boot time | CPU price | Differentiator |
|---|---|---|---|
| E2B | ~1-2s | $0.0504/vCPU-hr (per-second billing) | Pioneer, broad SDK support, MCP-native |
| Modal Sandboxes | <1s warm | $0.1419/physical core-hr | GPU-first, serverless control plane, large memory profile |
| Daytona | ~90ms | $0.0504/vCPU-hr + $0.0162/GiB-hr | OSS heritage, dev-environment focus, lowest published among microVM vendors |
| CodeSandbox SDK | ~2s | $0.01486/credit (variable by VM) | Browser-first, microVM, deep IDE/preview integration |
| GitHub Codespaces | seconds | $0.18-$2.88/hr by VM size + $0.07/GB/mo storage | Native to GitHub, lock-in via repo permissions |
| Replit Sandboxes | seconds | bundled in Replit consumption | Used heavily for Replit Agent itself |
| Vercel Sandbox | seconds | bundled in v0 / Vercel plans | Optimized for Next.js / web app generation |
| Northflank | seconds | $0.01667/vCPU-hr | Multi-tenant PaaS heritage, low published rate |

## Architecture Patterns

**Microvm + warm pool.** E2B, Daytona, CodeSandbox, Modal all run firecracker-style microVMs from snapshots. A warm pool ensures sub-second cold start. The agent's first API call resumes a paused VM rather than booting Linux from scratch.

**Per-second / per-CPU-hour billing.** Standard across the category. Bills only for active CPU time. This made sandboxes economical for agent workloads that are bursty by nature (an agent thinks for 30 seconds, executes for 2 seconds, thinks again).

**MCP-native.** Most providers now expose their sandbox as an MCP server — letting any agent harness that speaks MCP (Claude Code, Cline, Codex CLI, Aider) drop in sandbox execution without bespoke SDK integration.

**Snapshot / fork.** Newer feature: snapshot a sandbox mid-execution and fork it. Agents use this for speculative execution (try N solutions in parallel from a shared state).

## Use Cases

1. **Background agents.** Cursor Agents, Devin, Jules, Codex cloud all rent E2B / Modal / Daytona / their own internal sandboxes.
2. **Vibe-coding deploys.** Lovable spins up a sandbox per project to preview the running app.
3. **Agentic CI/CD.** Pre-merge agents that test PRs in isolated environments.
4. **Notebook agents.** Data science agents executing pandas / matplotlib code on user uploads.
5. **Eval harness.** SWE-bench runs require fresh containers per task; vendors use sandbox providers to scale these evals.

## Tradeoffs

| Dimension | Cloud sandbox | Local devcontainer | Ephemeral VM (raw cloud) |
|---|---|---|---|
| Boot time | 100ms-2s | 5-60s | 30s-2min |
| Isolation | strong | strong | strongest |
| Cost (idle) | $0 | uses local resources | hourly VM rate |
| Agent SDK | first-class | bespoke | bespoke |
| Persistence | optional, snapshot-based | per-session | manual |
| Best for | autonomous agents at scale | dev pair-programming | one-off heavy workloads |

See [[Code Execution Environments]] for the broader spectrum.

## Funding and Strategic Position

The sandbox layer is being acquired and bundled aggressively in 2026 as ADE vendors move up-stack:
- E2B remains independent; venture-backed.
- Modal raised at unicorn-plus valuation through 2025; sandbox is one product within a broader serverless compute play.
- Daytona pivoted from "self-hosted dev environments" (2023) into managed agent sandboxes (2025) and is now a primary OSS alternative to E2B.
- CodeSandbox SDK is the platform-product layer of CodeSandbox.io, monetized separately from the consumer IDE.

The structural prediction: sandbox compute will be either commoditized to within 2x of raw cloud VMs (margin compresses), or vertically integrated into ADE vendors (Cursor, Cognition, Lovable run their own pools). The independent middle layer is the most uncertain bet in the stack.

## See Also
- [[Code Execution Environments]]
- [[Model Context Protocol (MCP)]]
- [[Agent Harness]]
- [[Pricing Models]]
