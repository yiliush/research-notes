---
tags: [concept]
created: 2026-05-28
---

# Code Execution Environments

Every coding agent eventually executes code. Where it executes that code — the local machine, a devcontainer, a cloud sandbox, an ephemeral VM, or a WebContainer in the browser — shapes the agent's capabilities, security posture, latency, and unit economics. Mid-2026 has converged on a spectrum of three to four common patterns rather than one winner.

## Pattern 1: Direct local execution

Agent runs on the developer's machine. Claude Code, Codex CLI, Cline, Aider, Gemini CLI default to this.

**Pros.** Zero infra overhead. Full access to developer's tools, secrets, network. No data egress. Cheapest at small scale.

**Cons.** No isolation — agent writes and runs arbitrary code on the developer's machine. Mitigations include per-tool approval, allowlist commands, and read-only mode. Concurrency is bounded by the laptop. Async / overnight runs require the laptop to stay on.

Most popular for pair-programming style use; this is what the average power user runs.

## Pattern 2: Local devcontainer

Agent runs the developer's local IDE (Cursor, Windsurf, VS Code) but executes code inside a Docker-based devcontainer or local microVM. GitHub Dev Containers (`devcontainer.json`) is the standard spec.

**Pros.** Strong isolation, reproducible environment, defined dependencies, OS-agnostic. The agent can `rm -rf` inside the container without harming the host. Mature tooling.

**Cons.** Container cold start adds latency. Mac/Windows users pay Docker Desktop overhead. Local CPU/RAM bounds parallelism.

This is the standard pattern for security-conscious teams that still want local-feeling agents.

## Pattern 3: Cloud sandbox (microVM)

Agent (or the agent's backend) provisions an E2B / Modal / Daytona / CodeSandbox sandbox per task. Code executes there.

**Pros.** True multi-tenant isolation. Massive parallelism — hundreds of concurrent agent runs per organization. Async workflows (close laptop, agent keeps working). Per-second billing. Snapshot / fork.

**Cons.** Network egress costs and latency for repo clone + dependency install. Secrets management — agent needs access to private deps, registries, env vars without leaking them. Annual cost can exceed local hardware at scale.

This is the default for async agents (Devin, Jules, Codex cloud, Cursor Agents) and for vibe-coding (Lovable, v0, Bolt.new — though Bolt uses WebContainers instead).

See [[Cloud Sandboxes]] for vendor comparison.

## Pattern 4: Ephemeral VM (raw IaaS)

Agent provisions a full EC2/GCE/Fly machine, runs the task, tears it down. Jules' use of GCP VMs sits here.

**Pros.** Strongest isolation. Full kernel control. Suited to heavyweight tasks (build farms, large simulations, GPU work).

**Cons.** Boot times measured in tens of seconds to minutes. Higher minimum cost. Lifecycle management overhead. Not economical for small bursty tasks.

Mostly used by hyperscaler-owned async agents (Jules → GCP VMs, Codex cloud → presumed Azure backend), where the cost and lifecycle are absorbed by the platform.

## Pattern 5: Browser WebContainer

StackBlitz's WebContainers run a Node.js environment entirely in the browser via WebAssembly. Bolt.new is the canonical agent host.

**Pros.** Zero server-side compute cost. Instant boot (no network). Highly economical at scale. No data egress.

**Cons.** Constrained to JavaScript / Node-ish stacks. Can't run native binaries, Python with C extensions, GPUs, or persistent services. Browser memory limits.

A wedge into the vibe-coding market specifically — works because most prompt-to-app flows produce JS apps.

## The Trade Space

| Pattern | Boot time | Isolation | Parallelism | Cost at scale | Best for |
|---|---|---|---|---|---|
| Direct local | instant | none | 1 | $0 marginal | individual power users |
| Local devcontainer | seconds | strong | low | $0 marginal | security-conscious individuals |
| Cloud sandbox | sub-second to seconds | strong | huge | $0.05-0.15/CPU-hr | async / background agents |
| Ephemeral VM | tens of seconds | strongest | huge | $0.05-1+/hr | heavyweight platform agents |
| Browser WebContainer | instant | strong | huge | $0 marginal | JS vibe-coding |

## How vendors mix patterns

- **Cursor** — local execution by default in the IDE; Cursor Agents (async) use a managed cloud backend.
- **Claude Code** — local execution; tool calls run on the user's machine.
- **Codex CLI** — local; Codex cloud is sandboxed.
- **Devin** — always cloud-sandboxed; never local.
- **Jules** — clones to GCP VM; always cloud.
- **Bolt.new** — WebContainer in browser.
- **Lovable** — cloud sandbox with deploy targets (Netlify / Supabase / Vercel).
- **Replit Agent** — sandbox inside Replit's existing dev environment, the same one humans edit.

## Future direction

Snapshot-and-fork is becoming the table-stakes feature: snapshot a paused sandbox, fork N copies, let agents explore in parallel, keep the winning fork. E2B, Modal, and Daytona all expose this. This pattern is what enables "speculative agent" workflows that try multiple solutions and pick the best — and it makes the cloud-sandbox pattern strictly more capable than local execution for autonomous agents.

## See Also
- [[Cloud Sandboxes]]
- [[Agent Harness]]
- [[Model Context Protocol (MCP)]]
