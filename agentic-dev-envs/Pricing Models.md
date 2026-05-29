---
tags: [market]
created: 2026-05-28
---

# Pricing Models

ADE pricing fragmented into five distinct models in 2025 and has begun consolidating in 2026 as vendors hit unit-economics walls. Per-seat is simple but cannibalized by power-user token burn. Per-token is honest but illegible to procurement. Per-task and credit-based create predictable bills but require accurate cost prediction. BYOK is the escape hatch enterprises use when nothing else fits.

## Model 1: Seat-based (the default)

- **GitHub Copilot.** $10/user/mo Individual, $19/user/mo Business, $39/user/mo Enterprise. Cheapest in the market; effectively unmetered for typical use.
- **Cursor.** $20/mo Pro, $40/user/mo Business, custom Enterprise. Includes a generous request quota; power users hit "unlimited" with degradation rather than overage.
- **Windsurf (now Cognition's IDE).** Similar seat-based for the editor surface.
- **JetBrains AI Assistant.** $10-30/mo bundled into IDE subscription.

Tradeoffs: predictable budget, easy procurement, but power users (who run agents continuously) burn margins. Vendors have responded with rate limits, model-tier downgrades, and "fair use" enforcement.

## Model 2: Per-token / consumption (the honest layer)

- **Claude Code.** Effectively per-token via Anthropic API or via Max/Team Premium subscriptions that bundle a token budget. Empirical enterprise spend: ~$13/dev/active day, $150-250/dev/month with Sonnet 4.6. Sonnet 4.6 list: $3 input / $15 output per million tokens. Haiku 4.5: $1/$5.
- **Cody (Sourcegraph).** Per-message and per-token tiers above seat baseline.
- **Codex CLI.** Bundled with ChatGPT Plus/Pro/Team/Enterprise, but heavy users effectively pay via plan tier.
- **OpenAI / Anthropic API direct.** What BYOK-style harnesses (Aider, Cline) re-package.

Tradeoffs: aligns cost to value, but procurement teams hate variable bills. Enterprises mitigate via budgets, alerts, model-tier ceilings.

## Model 3: Per-task / per-ACU (autonomous-only)

- **Devin (Cognition).** $20/mo Core entry (introduced when Devin 2.0 dropped from $500); Team is $500/mo + 250 Agent Compute Units (1 ACU ≈ 15 min of autonomous work, $2 each beyond plan). Enterprise is custom with volume discounts. Realistic enterprise spend frequently runs back to $300-500/dev/mo.
- **Codex cloud.** Task-priced for managed agent runs.
- **Jules (Google).** Bundled with Gemini Pro plan; Jules API for external orchestration is metered.

Tradeoffs: matches the agent paradigm — pay for outcomes, not seats — but ACU prediction is poor and bills surprise. Cognition added Core tier to undercut sticker shock.

## Model 4: Credit-based (consumer / vibe-coding)

- **Replit.** Consumption credits for Agent runs, deploys, autoscale. Targeting $1B ARR by EOY 2026 against $9B valuation; pricing is the load-bearing element.
- **Lovable.** Credit-based per project / per message; tiered free/paid. Drove $0 → $400M ARR in roughly 12 months.
- **v0 (Vercel).** Credit-based per generation; $40M ARR.
- **Bolt.new (StackBlitz).** Free tier of 1M tokens/month; paid tiers above.

Tradeoffs: intuitive for non-engineers, monetizes engagement directly. Drives extreme growth but is sensitive to model cost shocks.

## Model 5: Free + BYOK (open-source)

- **Cline, Aider, Continue, Goose, OpenHands.** Free clients; user pays the model provider directly. No vendor margin between developer and tokens.
- **Cline Teams (paid).** Organization management, billing aggregation, self-hosted deployment — sold above free agent.
- **Continue Enterprise.** Self-hosted control plane on top of OSS.

Tradeoffs: zero acquisition cost, maximum control. Vendors monetize via enterprise tier (team management, security, deployment), not the agent itself.

## Sandbox / Infrastructure Pricing (the layer below)

For context on what agent execution actually costs at the compute layer:

| Provider | CPU rate | Notes |
|---|---|---|
| Northflank | $0.01667/vCPU-hr | lowest published |
| E2B | $0.0504/vCPU-hr | per-second billing |
| Daytona | $0.0504/vCPU-hr + $0.0162/GiB-hr | dev-env heritage |
| Modal Sandboxes | $0.1419/physical core-hr | serverless premium |
| GitHub Codespaces | $0.18-2.88/hr by VM size | + $0.07/GB/mo storage |

See [[Cloud Sandboxes]] for full breakdown.

## Trends and Tradeoffs (May 2026)

1. **Seat pricing is dead at the high end.** Cursor, Anthropic, and Cognition all moved their power-user/enterprise tiers toward usage-aligned billing or generous-bundle-with-throttle pricing. Copilot is the holdout.
2. **Per-task pricing requires great cost prediction.** Devin's ACU bill surprises were the first big object lesson. Every async-agent vendor now ships budget controls, dry-run cost estimates, and hard caps.
3. **BYOK is winning regulated industries.** Enterprises with negotiated frontier-lab contracts won't double-pay; they want a harness that routes to their own keys. Cline and Continue exploit this.
4. **Vibe-coding pricing is the most fragile.** Lovable / v0 / Replit Agent margins depend on model costs holding steady. Each frontier-lab price cut is upside; each price hike is a margin event.
5. **Hyperscaler bundling.** Microsoft bundles Copilot into Visual Studio Enterprise; Google bundles Antigravity into Workspace; AWS will likely bundle Kiro into AWS contracts. This is the structural pressure on standalone vendors.

## See Also
- [[Market Landscape]]
- [[Enterprise Adoption]]
- [[Cloud Sandboxes]]
- [[Competitive Dynamics]]
