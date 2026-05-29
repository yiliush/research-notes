---
tags: [infrastructure, sandbox, daytona, open-source, ade-cluster]
created: 2026-05-28
---

# Daytona

Daytona is the open-source sandbox provider that pivoted hard from "self-hosted dev environments for humans" (2023) to "stateful agent sandboxes" (2025–2026) and is now the primary OSS alternative to [[E2B]]. The thesis: cloud infrastructure was built for humans typing into terminals; agents need a different shape — programmatic, composable, snapshot-friendly, sub-second.

## Company / Origin
- Founded by Ivan Burazin, who previously ran Codeanywhere (one of the early browser IDEs, acquired in 2021). Daytona launched 2023 as an open-source orchestrator that let teams self-host pre-configured dev environments per repo — essentially "your own Codespaces."
- Pivot story: the OSS project picked up significant traction with agent startups using it as the substrate for sandboxes, not for humans. The team leaned in and rebuilt Daytona around agent-shaped primitives (snapshot, fork, pause, programmatic start) in 2025.
- Daytona Cloud: the managed service launched 2025, providing the sandbox API without the self-hosting.

## Funding & Adoption
- Pre-seed Nov 2023: $2M.
- Seed June 2024: $5M led by Upfront Ventures.
- Series A Feb 2026: $24M led by FirstMark Capital (Matt Turck joining the board), with Pace Capital, Upfront, E2VC, Darkmode, plus strategic checks from Datadog and Figma Ventures. Total ~$31M raised.
- Revenue: $1M forward ARR within three months of the pivot, doubled six weeks later — a fast ramp from a low base.
- Open-source repo (daytonaio/daytona) has heavy GitHub traction; community uses it both self-hosted and via Daytona Cloud.

## Architecture
- Firecracker-style microVMs under the hood, started from pre-warmed snapshots.
- **~90ms cold start** — the lowest published figure among microVM sandbox vendors as of 2026, achieved through aggressive snapshot warming and a custom rootfs.
- The agent-shape primitives the team standardized around: `start`, `stop`, `pause`, `resume`, `fork`, `snapshot`, `destroy`. Fork is the differentiated one — it lets agents do speculative execution (run N approaches in parallel from a shared mid-task state).
- Resource model: CPU, memory, storage, GPU, networking, OS all configurable per sandbox. Stateful by default — agents can keep a sandbox alive across many tool calls.
- Multi-plane architecture: Interface plane (SDK, MCP server, dashboard) → Control plane (orchestration) → Data plane (the actual microVM fleet).
- Self-host option: same daemon and orchestrator that runs Daytona Cloud is open source under Apache 2.0. Customers can run it on their own AWS/GCP/bare metal — a real differentiator against E2B and Modal.
- MCP server first-class.

## Pricing
- Daytona Cloud: $0.0504/vCPU-hour + $0.0162/GiB-hour, per-second billing.
- Free tier with credit on signup.
- Self-hosted: free, infrastructure costs only.
- Enterprise plans for dedicated capacity and air-gapped deployments.

## Strategic Position
- The OSS-and-self-hostable angle is the key wedge against E2B. Customers in regulated industries (finance, defense, healthcare) and customers worried about lock-in have a real reason to pick Daytona.
- Datadog and Figma as strategic investors hint at integration paths — Datadog on observability for agent fleets, Figma on design-tool-to-code agents.
- Direct competition: E2B (closest), Modal (different architecture), CodeSandbox (browser heritage). Vercel Sandbox and Cloudflare's agent sandboxes are platform-bundled threats from above.
- Has positioned aggressively as "the agent-native cloud" — explicitly rejecting human-developer use cases that Codespaces and Gitpod still chase.

## See Also
- [[Cloud Sandboxes]]
- [[E2B]] — direct competitor
- [[Modal Sandboxes]]
- [[CodeSandbox]]
- [[GitHub Codespaces]]
- [[Devcontainers]]
- [[Code Execution Environments]]
