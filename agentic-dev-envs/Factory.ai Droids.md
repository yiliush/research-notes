---
tags: [company/factory, async-agent, autonomous-coding, droids, enterprise]
created: 2026-05-28
---

# Factory.ai Droids

Factory.ai sells "Droids" — agent-native software development units that handle full development-lifecycle tasks (features, migrations, on-call triage) for enterprises. They positioned themselves explicitly against the copilot framing: agents handle tasks; humans handle architecture and review.

## Background

- **Maker:** Factory AI, founded 2023, San Francisco.
- **Pitch:** Agent-native software development — not a copilot, not an IDE plugin. The atomic unit of work is a Droid that owns a task end-to-end.
- **Product naming:** "Droids" launched as the headline product at the Series B announcement on September 25, 2025.

## Funding & Traction

- **Series B (September 25, 2025):** $50M at $300M valuation. Led by NEA and Sequoia Capital, with Nvidia and J.P. Morgan participating. Angels include Frank Slootman (ex-Snowflake CEO), Nikesh Arora (Palo Alto Networks CEO), Aaron Levie (Box CEO).
- **Series C (2026):** ~$150M at ~$1.5B valuation, led by Khosla Ventures.
- **Enterprise customers (Factory disclosures, Sept 2025):** Ernst & Young, Nvidia, MongoDB, Zapier, Bayer, Clari.
- **Reported customer outcomes:** "31x faster feature delivery, 96% shorter migration times, 96% reduction in on-call resolution times" — vendor-reported, not independently audited.

## Architecture

- **Async, cloud-sandboxed agents** that complete a full task lifecycle.
- **Surfaces:** Slack, GitHub, Linear, Jira — Factory positions Droids as embedded across the existing toolchain rather than living in a separate UI.
- **Multi-Droid:** Different Droid types specialize (e.g., Tutorial Droid, Knowledge Droid, Code Droid).
- **Model backbone:** Frontier models (Anthropic, OpenAI); model-agnostic by design.
- **Benchmark:** Factory's Droids reportedly ranked #1 on Terminal-Bench at Series B launch — the terminal-task benchmark also referenced by Claude Code and Cursor. No published SWE-bench Verified score for the Droid product specifically.

## Pricing / Access

- **Sold per-seat / per-Droid to enterprises.** Public pricing is not disclosed in detail; Factory leads with enterprise sales motion.
- **No free tier or self-serve indie plan** comparable to Jules' free tier or Devin's $20 Core.

## Differentiators

- **"Agent-native" framing.** Explicitly rejects the copilot model — the verb is "delegate", not "assist".
- **Terminal-Bench #1 at launch.** Real benchmark traction on a non-SWE-bench leaderboard.
- **Enterprise list.** Nvidia and J.P. Morgan are both investors and reference customers, which is rare.
- **Toolchain embedding.** Lives in Slack/Linear/Jira rather than trying to own a new interface, which lowers adoption friction in big orgs.
- **Khosla-led Series C at $1.5B (2026)** validates the bet — Factory is the most credible challenger to Devin in the commercial async-agent tier.

## See Also

- [[Autonomous Coding Agents]]
- [[Devin]] — the obvious comparison
- [[Jules]]
- [[Codex Cloud]]
