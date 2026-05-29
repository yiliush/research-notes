---
tags: [tool, ide-extension, vscode, jetbrains, enterprise, incumbent]
created: 2026-05-28
---

# Tabnine

Tabnine is the oldest AI code completion company still standing — founded 2017, predating Copilot by four years — and the clearest example of an incumbent that survived the LLM transition by going hard into enterprise. It sunset its free tier in 2025, shipped its Enterprise Context Engine and agentic platform in early 2026, and now sells almost exclusively into regulated industries that need SaaS, VPC, on-prem, or air-gapped deployment. 9.4M+ VS Code installs is the largest in this cluster outside Copilot.

## Origin
- Maker: Tabnine Ltd. (formerly Codota; Codota acquired Tabnine and took the name)
- Founded 2017 in Tel Aviv, Israel
- License: Proprietary
- Funding: $102M total across 5 rounds; latest $25M in November 2023. Investors include Khosla Ventures, Headline, Telstra Ventures

## Adoption
- 9.4M+ VS Code Marketplace installs (May 2026) — largest non-Copilot install base in this cluster
- JetBrains marketplace installs in the millions
- ~72 employees
- Median enterprise contract ~$23K/year

## Architecture
- Model support: Tabnine-hosted proprietary models (trained on permissively-licensed code only), plus Claude, OpenAI, and Mistral routing for premium tiers
- BYOK: Enterprise tier supports private model deployment
- Agent harness: Tabnine Agents (early 2026) — code generation, test generation, code review, Jira/Atlassian tasks
- MCP support: Yes — added in the Agentic tier
- Codebase indexing: Enterprise Context Engine indexes the entire codebase, internal docs, Jira, Confluence, and connected systems
- Deployment: SaaS, VPC, on-prem, air-gapped — the breadth here is unmatched

## Pricing
- Free tier sunset in 2025
- Dev: free trial only
- Enterprise / Code Assistant: $39/user/mo
- Agentic: $59/user/mo (autonomous agents, MCP tools, unlimited codebase connections)
- Enterprise contracts: custom, often ~$23K/year median

## Differentiators
- Compliance posture: SOC 2 Type II, ISO 27001, GDPR, zero code retention by default, air-gapped deployment
- Permissively-licensed training data: defensible against IP-contamination lawsuits — the original positioning vs. Copilot
- Deployment breadth: only player offering air-gapped + on-prem + VPC + SaaS in a single product
- Enterprise Context Engine connects beyond code (Jira, Confluence, internal docs)
- Customer base skews regulated industries (banks, defense, healthcare)

## See Also
- [[VSCode Ecosystem]]
- [[GitHub Copilot]]
- [[Cody]]
- [[Augment Code]]
