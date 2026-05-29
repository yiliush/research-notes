---
tags: [company, ai-ide, aws, kiro, ade-cluster, spec-driven]
created: 2026-05-28
---

# Kiro

Kiro is AWS's spec-driven agentic IDE, launched in public preview at the AWS Summit New York on July 15, 2025 and reaching general availability November 17, 2025 at re:Invent. It is AWS's structural answer to [[Cursor]] and the explicit champion of [[Spec-Driven Development]] inside the hyperscaler tier — a deliberate counterprogramming move against [[Vibe Coding]]. AWS is also winding down [[Amazon Q Developer]]'s IDE plugins and migrating those users to Kiro.

## Product

- VS Code fork with a Spec mode and a Vibe mode. Spec mode is the default and the differentiator.
- **Specs**: when you describe a feature, Kiro generates three files: `requirements.md` (user stories + acceptance criteria in EARS notation — "WHEN [condition] THE SYSTEM SHALL [behavior]"), `design.md` (architecture, sequence diagrams, implementation notes), and `tasks.md` (the agent-executable work breakdown). The spec is the artifact; code is downstream.
- **Steering files**: `.kiro/steering/product.md`, `tech.md`, `structure.md` — workspace-scoped context the agent consults for every action. Conceptually similar to [[AGENTS.md Standard]] but with mandatory structure.
- **Agent Hooks**: file-event, lifecycle-event, and spec-task-event triggers that run agent actions automatically. The mechanism for "every time a TypeScript file is saved, update the corresponding test" style automation.
- **EARS notation** is the specification language — chosen because vague requirements produce vague code.
- Multi-agent orchestration and CLI parity (Kiro CLI) added at GA.

## Pricing

Three-tier model announced for GA:
- Free: 50 agent interactions/user/month — light experimentation only
- Pro: $19/user/month — 1,000 interactions
- Pro+: $39/user/month — 3,000 interactions

Pricing is per-interaction, not per-token — distinct from the Cursor/Anthropic model. AWS Startups offers one year of Pro+ free to qualifying startups, the credit-driven adoption playbook AWS has run since the EC2 era.

## Strategic Position

- Kiro is AWS's flagship developer-AI product going forward. The April 2026 [[Amazon Q Developer]] end-of-support announcement (IDE plugins sunset April 30, 2027) confirmed Kiro is the replacement — Q Developer survives only in terminal/AWS-console form.
- The spec-driven thesis is AWS's bet that the next phase of agentic coding is constrained by requirements quality, not model quality. Kiro is engineered around the claim that the vibe-coding loop (prompt → accept → debug) is a symptom of skipping requirements, not a feature of LLMs.
- Distribution advantage: every AWS customer with credits is a target. The startup-credits deal is the same playbook that made AWS infrastructure dominant.
- Direct competitor to [[GitHub Spec Kit]] (an open methodology, not a product) and structurally similar to what [[Tessl]] has been arguing since 2024. Kiro is the first hyperscaler to make spec-first the default UX rather than an option.

## See Also

- [[Amazon Q Developer]] — the predecessor being sunset
- [[Spec-Driven Development]] — the methodology Kiro champions
- [[GitHub Spec Kit]] — the open-source counterpart
- [[Tessl]] — the spec-first independent
- [[AGENTS.md Standard]] — adjacent context-file convention (Kiro is in the Spec Kit integration list)
- [[Vibe Coding]] — the failure mode Kiro is positioned against
- [[AI-Native IDEs]]
