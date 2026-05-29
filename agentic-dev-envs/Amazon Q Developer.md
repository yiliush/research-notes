---
tags: [company, ai-coding, aws, amazon-q, codewhisperer, ade-cluster]
created: 2026-05-28
---

# Amazon Q Developer

Amazon Q Developer is AWS's agentic coding assistant, the renamed and expanded successor to CodeWhisperer (rebranded April 2024). It runs in IDE plugins (VS Code, JetBrains, Visual Studio, Eclipse), the terminal, and the AWS console. As of April 2026 AWS has announced the IDE plugin product is being sunset — new signups end May 15, 2026 and full end-of-support is April 30, 2027 — with users migrated to [[Kiro]]. Q Developer survives as the terminal and AWS-console agent; [[Kiro]] is the IDE story going forward.

## Product

- **IDE plugin agentic mode** (Claude Sonnet 3.7 backed at the last update) — multi-turn task execution, codebase-aware edits, transparent reasoning.
- **CLI / terminal agent** — natural-language shell, AWS-aware command construction, persistent context.
- **AWS console integration** — Q answers infrastructure and billing questions inside the console itself.
- **Code transformation** — automated Java 8/11/17 → 17/21 upgrades; .NET Framework → .NET Core migrations. Capacity quoted at 1,000–4,000 lines/user/month on paid tiers.
- **MCP support** in IDE plugins (June 2026 addition — though now mostly relevant for the Kiro migration path).
- **Compliance**: SOC, ISO, HIPAA, PCI eligible. Reference tracking, public-code suppression, per-user indemnity.

## Benchmarks

- SWE-bench Verified: 66% (April 2026) — AWS claimed top-of-leaderboard at the time of announcement. See [[SWE-bench and Coding Benchmarks]].

## Traction

- AWS-disclosed (internal Amazon usage): $260M in annual cost savings and 4,500 developer-years saved via Q-assisted modernization. Tens of thousands of production apps migrated from Java 8/11 to 17.
- Amazon Q Business (the adjacent enterprise-knowledge product) resolved 1M+ internal Amazon developer questions and cut technical query time by 450,000+ hours.
- Public per-seat subscriber numbers not disclosed. For comparison, [[GitHub Copilot]] reported 1.3M+ paid seats in early 2024.
- Distribution: 19 AWS regions (11 default + 8 opt-in) — the broadest regional footprint of any AI-coding product.

## Strategic Position

- The April 2026 end-of-support announcement reframes Q Developer's position: it is no longer AWS's flagship developer-AI product. [[Kiro]] is. Q Developer is now the terminal/AWS-console agent, not the IDE.
- The migration to Kiro is AWS's bet that spec-driven development is the durable model and that Q Developer's prompt-driven plugin paradigm is a 2023–2025 generation product.
- Enterprise traction (especially Java modernization) is the moat — Q Developer's code-transformation flows have an installed base of large refactor jobs that Kiro will need to absorb. PwC and other systems integrators sell Q Developer modernization as a managed service.

## See Also

- [[Kiro]] — the successor for IDE workflows
- [[GitHub Copilot]] — the incumbent Q Developer was originally positioned against
- [[Cursor]]
- [[SWE-bench and Coding Benchmarks]]
- [[CLI Coding Agents]]
- [[Enterprise Adoption]]
