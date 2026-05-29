---
tags: [infrastructure, sandbox, replit, ade-cluster]
created: 2026-05-28
---

# Replit Sandboxes

Replit Sandboxes are the VM-and-container execution layer underneath Replit's IDE, Replit Agent, and Replit Deployments. They are not currently sold as a standalone product (Replit's revenue comes from its consumer/prosumer subscriptions and from Replit Agent), but they are the substrate on which Replit Agent runs and one of the most-used agent sandboxes in absolute volume because of Replit Agent's consumer scale.

## Company / Origin
- Replit, Inc., founded 2016 by Amjad Masad, Faris Masad, and Haya Odeh. HQ San Francisco.
- Started as a browser-based REPL for educational use; expanded into a full-IDE-in-the-browser, hosting, deployments, and (2024) Replit Agent — the prompt-to-running-app product.
- Sandboxes evolved organically: every Repl is, in effect, a sandbox VM. When Replit Agent shipped, those VMs became the agent's execution substrate by default.

## Funding & Adoption
- Series B 2023 at $1.16B valuation; subsequent rounds in 2024–2025 reportedly pushed valuation higher amid the AI wave. Total raised >$200M.
- Replit Agent ARR crossed $100M in 2025 per reporting; total Replit user base 30M+ accounts.
- Replit Agent 3 and Agent 4 shipped through 2025–2026, with each iteration tightening the loop between agent action and live preview.

## Architecture
- Each Repl runs in a **Replit-managed Linux VM**, traditionally an Nix-based environment with reproducible package management. Boot time: seconds.
- Underlying isolation has been a mix of containerization plus VM boundaries; details are not as publicly documented as E2B or Modal. Replit has publicly committed to "defense in depth" architecture after the 2025 incident where a Replit Agent was prompt-injected into running destructive commands in a user environment — the incident drove a substantial hardening pass.
- Persistence: every Repl has a persistent filesystem; Replit's storage layer handles hibernation/resume.
- Networking: each Repl gets a public URL, a forwarded port, and (for paid tiers) a custom domain.
- Replit Database, Object Storage, and Secrets are first-class sandbox-attached services.
- Replit Agent uses a wrapper around these primitives: code workspace + runtime container + DB + secrets + deploy pipeline + chat-style agent loop.

## Pricing
- Sandboxes are bundled into Replit's consumer/team subscriptions, not metered as separate units to end users.
- Replit Core: $25/month including AI credits and Always-On Repls.
- Teams and Enterprise tiers add SSO, audit logs, larger compute.
- Replit's internal cost-per-sandbox is competitive with the microVM vendors at their scale, since Replit owns the orchestration stack end-to-end.

## Strategic Position
- Replit's sandboxes are vertically-integrated: they exist to make Replit Agent and Replit Deployments work, not to be sold as a primitive. This is the structural opposite of E2B's strategy.
- The Replit Agent scale (30M user accounts, consumer reach the agent-infra startups don't have) means Replit operates one of the largest agent-sandbox fleets in the world by raw volume.
- The 2025 prompt-injection incident is now studied across the category as the case study for why sandbox isolation has to assume the agent itself is adversarial — not just user code.
- Competitive positioning: Replit competes directly with Lovable, Bolt.new, v0 in vibe-coding; competes obliquely with E2B/Daytona/Modal as a sandbox provider it never sells. See [[Replit]] and [[Replit Agent]] for the product side.

## See Also
- [[Replit]]
- [[Replit Agent]]
- [[Cloud Sandboxes]]
- [[Bolt.new]]
- [[v0]]
- [[Lovable]]
- [[Vibe Coding Platforms]]
