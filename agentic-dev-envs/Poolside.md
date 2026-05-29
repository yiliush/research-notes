---
tags: [company, model-lab, frontier-code-model, enterprise, on-prem]
created: 2026-05-28
---

# Poolside

Poolside is the highest-funded "model is the moat" bet in code: Jason Warner left the GitHub CTO seat to build a coding-specialist frontier lab that ships sovereign model weights to Fortune 500 banks and defense contractors rather than competing with Cursor on IDE UX. As of May 2026 it has raised ~$626M against a reported $12B valuation and remains one of the most quietly-marketed labs in the cohort — by design, since most of its customers cannot publicly acknowledge they use it.

## Company / Origin
- Founded 2023 by Jason Warner (ex-CTO GitHub, ex-VP Engineering Heroku and Canonical) and Eiso Kant (ex-CTO Athenian).
- HQ: Paris, France with significant US presence. The French HQ is strategic — sovereign-AI procurement in EU and Gulf states is a major target market.
- Headcount: ~150 as of early 2026 (per Contrary Research, Tracxn).

## Funding & Valuation
- Seed 2023: ~$26M, Redpoint Ventures led
- Series A May 2024: ~$100M
- Series B October 2024: $500M led by Bain Capital Ventures and DST Global, at $3B valuation, with eBay, NVIDIA, Felicis Ventures, S Ventures (SentinelOne), and StepStone participating (TechCrunch, Oct 2 2024)
- Reported 2025 secondary / extension activity pushing implied valuation to ~$12B (Sacra, Tracxn data as of May 2026)
- Total reported raised: ~$626M
- The "Project Horizon" 2GW Texas data center partnership with CoreWeave was reported to have collapsed in early 2026 (per tech-insider.org reporting), a notable setback for their compute roadmap.

## Product / Models
- **Malibu** — flagship frontier coding model, beta mid-2025. Failed to clear 70% on SWE-bench Verified (reported low-to-mid 60s), well behind Claude Sonnet 4.6 (79.6%) and Claude Opus 4.6 (80.8%).
- **Laguna XS.2** — released April 2026, 33B-parameter open-weight model for local agentic coding. Hits 68.2% on SWE-bench Verified — competitive with the best open models at that parameter count.
- **Laguna M.1** — larger sibling, 72.5% SWE-bench Verified per their April 2026 release.
- Architecture: proprietary, trained on a mix of permissively-licensed code, synthetic execution traces ("Reinforcement Learning from Code Execution Feedback", their internal RLCEF), and customer code in dedicated training environments.
- Available on AWS Bedrock as of 2025.

## Distribution
- Primary channel: direct enterprise sales. Each Fortune 500 customer gets a dedicated training environment inside their own infrastructure ("spins up dedicated training environments within the client's infrastructure" per their published GTM).
- Customers (named or strongly-implied): Fortune 500 banks (multiple), two top-five US defense contractors, European industrial conglomerates.
- On-prem / air-gapped: yes — model weights ship in fully isolated environments and can run offline. This is the entire pitch. Most agents in the [[Agent Harness]] cluster cannot do this.
- API: limited public API access. Bedrock listing is the closest to a generally-available channel.

## Strategic Position
- Bets that the bottleneck for enterprise adoption is not IDE UX but data sovereignty, IP indemnification, and on-prem inference. This is a real, underserved market — [[Cursor]], [[Claude Code]], and [[GitHub Copilot]] all struggle here, especially with defense and regulated finance.
- Vulnerable to two threats: (1) open-weight frontier models from [[DeepSeek]] and [[Qwen Coder]] collapse the value of paying for proprietary weights when the same Fortune 500 customer could deploy Qwen3-Coder behind their own firewall for free; (2) Anthropic, OpenAI, and Google increasingly offer on-prem / dedicated VPC deployments that close the sovereignty gap.
- Malibu's SWE-bench miss is the weakest part of the story — if you're charging a frontier-lab premium, you need frontier-lab benchmarks. Laguna's open-weight performance is more credible but cannibalizes the Malibu pricing pitch.
- Warner's personal credibility with engineering leadership at large enterprises (he ran the GitHub CTO org through Copilot's birth) is arguably their biggest moat — bigger than the model itself.

## See Also
- [[Coding Model Labs]]
- [[Magic.dev]] — peer in stealth-frontier-code category
- [[Reflection AI]] — peer
- [[DeepSeek]] — open-weight threat
- [[Qwen Coder]] — open-weight threat
- [[GitHub Copilot]] — Warner's alma mater
- [[Enterprise Adoption]]
