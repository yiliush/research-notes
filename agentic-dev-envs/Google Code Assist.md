---
tags: [company, ai-coding, google, gemini-code-assist, duet-ai, ade-cluster]
created: 2026-05-28
---

# Google Code Assist

Gemini Code Assist is Google's IDE plugin product, the rename of Duet AI for Developers (rebranded early 2024). It runs as extensions in VS Code, JetBrains, Android Studio, and Cloud Workstations, and ships in free, Standard, and Enterprise editions. As of May 2026 the product is on a sunset path: Google announced that Gemini Code Assist IDE extensions and Gemini CLI for individual / AI Pro / AI Ultra tiers stop serving requests June 18, 2026, with users migrated to [[Antigravity]]. Enterprise edition continues for now.

## Product

- **Gemini 2.5 backend** with a 1M-token context window — the largest of any IDE plugin and the explicit differentiator vs [[GitHub Copilot]] and [[Cursor]].
- **Features**: code completion, comment-to-function generation, unit-test generation, debug/explain/document flows. Standard tab + chat IDE workflow.
- **Enterprise edition**: code customization trained on the customer's codebase, higher quotas, admin controls, audit logging, integration with Duet AI surfaces across Google Cloud (BigQuery, Cloud Run, etc.).
- **Gemini CLI**: open-source terminal agent shipped alongside Code Assist, bundled into the same entitlement.
- **IDE coverage**: VS Code, JetBrains family, Android Studio, Cloud Shell Editor, Cloud Workstations.

## Pricing (May 2026)

- Free: 180,000 monthly code completions (~6,000/day) and 240 chat interactions/day — the most generous free tier in the category.
- Standard: $19/seat/month (annual) or $22.80/month
- Enterprise: $45/seat/month (annual) or $54/month — adds codebase customization, audit, Cloud integrations

## Strategic Position

- Code Assist was Google's holding pattern in the AI-IDE race from 2023 through mid-2025 while Google paid catch-up on coding-specific models. The product never displaced [[GitHub Copilot]] in enterprise distribution despite being a hyperscaler offering.
- The acquihire of the [[Windsurf]] team (July 2025) and the launch of [[Antigravity]] (November 2025) shifted Google's strategy. Code Assist's individual tiers are being absorbed into Antigravity; Enterprise edition remains the corporate-IT story for organizations that need a plugin, not a new IDE.
- The Gemini-3 / Gemini-Code-Assist split has not been cleanly explained — as of May 2026 Google has multiple developer-AI surfaces (Code Assist, Antigravity, Stitch, AI Studio, Jules) and the consolidation is incomplete. Antigravity is the apparent end state; Code Assist Enterprise is the transitional product.
- The free tier remains the most aggressive in the market — 180K completions/month is roughly 30× what [[GitHub Copilot]] Free offers, a deliberate adoption-funding play while Google migrates the user base.

## See Also

- [[Antigravity]] — the successor for individual / AI Pro / Ultra tiers
- [[Gemini CLI]] — bundled with Code Assist, same sunset
- [[GitHub Copilot]] — the incumbent Code Assist was positioned against
- [[Cursor]]
- [[Stitch]]
- [[Jules]]
- [[VSCode Ecosystem]]
