---
tags: [infrastructure, sandbox, modal, serverless, ade-cluster]
created: 2026-05-28
---

# Modal Sandboxes

Modal Sandboxes are the agent-execution primitive inside Modal Labs' broader serverless-compute platform. Where E2B was sandbox-first, Modal arrived from the other direction: a serverless GPU/CPU runtime for ML workloads that grew an agent use case once customers realized `modal.Sandbox` was the cleanest way to run untrusted code inside a Modal function.

## Company / Origin
- Modal Labs, founded 2021 by Erik Bernhardsson (CEO, ex-Spotify ML, creator of Annoy) and Akshat Bubna.
- Original positioning: serverless Python for ML — train models, run batch jobs, expose web endpoints, all from decorator-based Python. Sandboxes were a later primitive added once agent vendors started using Modal functions as ad-hoc execution layers.
- `modal.Sandbox` exposes a sandboxed container the user's Modal app can spawn at runtime, distinct from a Modal function.

## Funding & Adoption
- Seed and Series A through 2022–2024 (totals ~$25M before Series B).
- Series B Sept 2025: $80M at $1.1B valuation.
- Series C late 2025 / early 2026: $355M at $4.65B valuation, led by General Catalyst and Redpoint, with Menlo, Bain Capital Ventures, and Accel. Round split into two tranches; early demand priced at $2.5B before second tranche moved up to $4.65B.
- ARR: ~$50M Feb 2026 → $300M+ ARR reported mid-2026, a 5x jump driven heavily by agent and inference workloads.
- Customer base spans the AI-native stack: Suno, Substack, Ramp, Quora, plus a long tail of agent startups using Sandboxes as their execution layer.

## Architecture
- Sandboxes run as containers on Modal's shared compute fleet — not Firecracker microVMs. Isolation is container-grade (gVisor + namespaces + cgroups) which is weaker than E2B's VM boundary but adequate for most agent workloads.
- Cold start: <1 second warm, ~2–4 seconds cold (depending on image size). Modal caches images aggressively per workspace.
- The big differentiators vs E2B:
  - **GPU sandboxes are first-class.** T4 through B200 are addressable as a single Python decorator. Critical for agents that need to run model inference, image generation, or local fine-tuning inside the sandbox.
  - **Massive memory profile.** Up to hundreds of GB per sandbox.
  - **Same control plane as Modal functions.** Agent vendors already running on Modal don't need a second SDK or auth flow.
- Networking: outbound by default; named tunnels for inbound.
- Persistence: Modal volumes can be mounted into sandboxes for state across runs.

## Pricing
- Sandbox CPU: $0.00003942 per core-second (~$0.1419/core-hour) — a 3x premium over the base Modal function rate ($0.0000131/core-second). The premium reflects non-preemption.
- Memory: $0.008/GiB-hour.
- GPU: $0.59/hr (T4) up to $6.25/hr (B200).
- US region carries a 1.25x multiplier; sandbox + US together = 3.75x the cheapest function rate.
- Plans: Starter (free, $30 credits, 100 containers, 10 concurrent GPUs) · Team ($250/month, $100 credits, 1000 containers, 50 GPUs) · Enterprise.

## Strategic Position
- The bet: agents will need GPU-adjacent execution (running smaller models locally, image/video generation, vision tasks). Modal owns that workload better than E2B does.
- Used heavily by ML-flavored agent products and by SWE-bench-style eval infrastructure where the bursty + parallel + GPU-occasional profile fits.
- Risk: container isolation is weaker than Firecracker, so customers with hard untrusted-code requirements (browser agents executing arbitrary user code) still prefer E2B or Daytona. Modal's response has been to add stronger isolation primitives without fully matching the microVM model.
- Adjacent competition: Modal also competes with Replicate (inference-focused), Beam, Banana, and the hyperscalers' serverless tiers — sandboxes are a fraction of the overall business, but a strategically important one.

## See Also
- [[Cloud Sandboxes]]
- [[E2B]] — sandbox-first competitor
- [[Daytona]]
- [[CodeSandbox]]
- [[Code Execution Environments]]
- [[SWE-bench and Coding Benchmarks]]
