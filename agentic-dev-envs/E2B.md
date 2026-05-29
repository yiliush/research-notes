---
tags: [infrastructure, sandbox, e2b, ade-cluster]
created: 2026-05-28
---

# E2B

E2B is the category-defining cloud sandbox provider for AI agents — a Prague-and-SF-based startup whose Firecracker-microVM runtime now sits underneath a huge fraction of every async coding agent shipped in 2025–2026. If Cursor is the IDE moat, E2B is the execution moat: the place where the code an agent writes actually runs.

## Company / Origin
- Founded 2023 by Vasek Mlejnsky (CEO) and Tomas Valenta, both Czech founders. Originally Prague-based; HQ now San Francisco.
- The original product was an "AI playground" before pivoting to sandbox-as-a-service when the team realized agent vendors were all rebuilding the same execution layer.
- Open-source SDK (Python + JS/TS) on top of a closed-source orchestrator. SDK has been downloaded 2M+ times monthly as of 2026.

## Funding & Adoption
- Pre-seed/seed 2023–2024 from Decibel and KAYA — ~$11M total before Series A.
- Series A, July 2025: $21M led by Insight Partners. Total raised: ~$35M.
- 500M+ sandboxes initiated to date.
- E2B claims 88% of Fortune 100 have an account; sandboxes initiated at >50% of Fortune 500.
- Named customers / use-cases: Perplexity (advanced data analysis, shipped in 1 week), Hugging Face (DeepSeek R1 replication), Manus (27-tool agent orchestration), and many of the agent harnesses listed under Strategic Position.

## Architecture
- Each sandbox is a **Firecracker microVM** running a Linux userland, started from a paused snapshot.
- Cold start: ~150ms typical, sub-second 99p — fast enough that the orchestrator does not need to keep warm pools per-tenant for most workloads.
- Strong kernel-level isolation (real VM boundary, not gVisor-style syscall filtering).
- Default 1 vCPU / 512MB → user-defined up to 8 vCPU / 8GB+ in Pro.
- Persistence: sandboxes can be paused (state snapshotted to disk) and resumed; lifetime up to 24 hours on Pro. Sub-second resume from snapshot.
- Filesystem: ephemeral by default; explicit persistent volumes are an option in Enterprise.
- Networking: each sandbox has outbound internet + a programmatically-exposed public URL per port (for previewing webapps from inside agents).
- SDK semantics: `Sandbox.create()` returns a handle; agents run shell commands, read/write files, attach to processes, and stream stdout. Filesystem-watching and process supervision built in.
- MCP server: E2B exposes its sandbox as an MCP tool so Claude Code, Cline, Codex CLI, etc. can drop it in without bespoke SDK.

## Pricing
- Hobby: free with one-time $100 credit; 20 concurrent sandboxes; max 1-hour sessions.
- Pro: $150/month; 24-hour sessions; configurable CPU/RAM; higher concurrency.
- Enterprise: custom; dedicated capacity, SOC 2, custom retention.
- Per-second compute billing: ~$0.0504 per vCPU-hour with RAM bundled. Per-second granularity is the key feature — agents that think for 30 seconds and execute for 2 only pay for 2.

## Strategic Position
- The default substrate for "I am an agent vendor and I need a sandbox" — the AWS-Lambda-of-agents positioning.
- Known to underpin (publicly or by reputation): Perplexity code interpreter, Hugging Face agents, Manus, many SWE-bench eval pipelines, and various YC-batch agent startups that don't want to build their own pool.
- Tension with vertically-integrated competitors: Cursor, Cognition, Replit all run their own sandbox pools to avoid the E2B markup at scale. The structural question (see [[Cloud Sandboxes]]) is whether E2B can hold the independent middle layer or whether margin compresses toward raw cloud.
- Closest direct competitor: [[Daytona]] (open-source, similar microVM model). [[Modal Sandboxes]] competes from a serverless-compute angle. [[CodeSandbox]] competes from a browser-IDE heritage.

## See Also
- [[Cloud Sandboxes]] — concept note
- [[Daytona]] — closest competitor
- [[Modal Sandboxes]]
- [[CodeSandbox]]
- [[Devin]] — async agent customer pattern
- [[Model Context Protocol (MCP)]]
- [[Code Execution Environments]]
