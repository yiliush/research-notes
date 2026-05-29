---
tags: [moc, cluster-index, specialty-agents, ade]
created: 2026-05-28
---

# Specialty Agents

While horizontal IDEs and CLI agents (Cursor, Copilot, Claude Code, Windsurf) compete for the developer's primary surface, a parallel wave of specialty agents has carved out depth in single slices of the SDLC. These tools rarely try to write your application from scratch. They sit on top of an existing workflow — pull requests, CI, on-call rotations, docs sites — and do one thing well. The bet is that vertical depth beats horizontal breadth once the underlying LLMs are commoditized.

## The thin agent thesis

Three forces favor specialists in the current ADE landscape:

1. **Distribution via existing rails.** Code review tools ride GitHub/GitLab webhooks. SRE agents ride PagerDuty/Slack. Doc agents ride existing docs pipelines. They do not need to win the IDE war to reach developers.
2. **Workflow-shaped data.** A code review agent sees every PR. An SRE agent sees every incident. A test agent sees every regression. The data exhaust from a narrow workflow becomes a moat that a horizontal coder cannot easily replicate.
3. **Pricing power per outcome.** Specialty agents sell measurable outcomes (PRs reviewed, incidents resolved, tests written, docs published) rather than generic tokens. CodeRabbit reportedly hit $40M ARR in April 2026 — entirely on PR review.

The risk: horizontal coding agents (Claude Code, Cursor, Cognition's Devin) are commoditizing the underlying capability. Many specialty agents are essentially [[Claude Code]] or GPT wrapped with workflow glue and a focused prompt. The winners will be those with proprietary indices, workflow data, or contractual lock-in (managed services).

## SDLC slice map

### Code review
The most crowded and most lucrative slice. The two breakout leaders both raised significant 2025 rounds.

- [[CodeRabbit]] — $60M Series B, $550M valuation, $40M ARR. GitHub Marketplace #1 app.
- [[Greptile]] — $25M Series A from Benchmark, $180M valuation. Graph-indexed codebase context.
- [[Diamond by Graphite]] — Folded into Graphite Agent. Bundled with Graphite's stacking platform.
- [[Qodo Merge]] — Formerly Codium PR-Agent. Open-source roots (10.5k stars), $40M Series A.
- [[Bito]] — $5.7M seed extension. Codebase awareness positioning. $15/user pricing.
- [[Korbit]] — Tutorial-style review feedback, free for OSS, $9-24 per dev.
- [[Ellipsis]] — YC W24, $2M seed, $20/dev. Auto-fix PRs in addition to review.
- [[Trag]] — Natural-language custom rules. Free hobby tier.

### Migration & refactoring
Slow burn, high contract value. Sells to enterprise platform teams, not developers.

- [[Moderne]] — $50M total, built on OpenRewrite (3.4k stars). Used by AWS Q and GitHub Copilot upgrade assistant under the hood. Fortune 500 customers.
- [[Grit.io]] — Acquired by Honeycomb April 2025. Pattern DSL for code migrations.
- [[Second.dev]] — YC W23 (relaunched on migrations). $1.9M pre-seed. $200/mo unlimited.
- [[Pythagora]] — Open-source GPT Pilot (33.7k stars). Now an all-in-one app-builder rather than pure migration.

### Testing & QA
Range from managed services (QA Wolf) to autonomous fuzz (Antithesis).

- [[QA Wolf]] — $36M Series B, $76M total. Managed E2E test service at fixed monthly fee.
- [[Antithesis]] — $47M seed at $215M valuation. Deterministic simulation testing from ex-FoundationDB team. Palantir, MongoDB, Ethereum.
- [[Tusk]] — YC W24, $2.1M raised. Records production traffic, replays for regression detection.
- [[Momentic]] — $19.2M total, $15M Series A. Natural-language E2E test authoring.

### Debugging
A nascent slice — Sentry's Seer is the most monetized. Charlie is the most agent-native.

- [[Charlie Labs]] — $10M seed. "Daemons" run on .md files. Linear-integrated TS engineer.
- [[Sentry Autofix Seer]] — Add-on at $40/active contributor. Bolted onto Sentry's $400M ARR observability base.

### On-call & SRE
The most concentrated funding in this cluster. Resolve.ai's $1B Series A valuation in Feb 2026 marked the first AI SRE unicorn.

- [[Resolve.ai]] — $125M Series A at $1B valuation. Ex-Splunk/OpenTelemetry founders.
- [[Cleric]] — $9.8M seed. Self-learning operational memory positioning.
- [[Sherlocks.ai]] — Multi-agent, VPC-deployed, smaller/earlier than the above.

### Docs & onboarding
Mintlify dominates the docs hosting layer; others target onboarding/codebase understanding.

- [[Mintlify]] — $67M total, $45M Series B at $500M valuation. $10M ARR. Anthropic, Microsoft, Coinbase as customers.
- [[Unblocked]] — $30M raised, $20M Series A. Codebase Q&A pulling from chat + tickets.
- [[Driver.ai]] — $8M seed led by GV. Simplifies existing technical docs.
- [[Pieces for Developers]] — Local-first dev memory layer. $19/mo.

### Repo intelligence
The "search the codebase" layer that other agents consume.

- [[Sourcegraph]] — $300M total. Sunset Cody Free/Pro in 2025. Launched Amp coding agent.
- [[CodeStory]] — YC S23, open-source Aide IDE (2.2k stars). Mistral-backed.

### Security agents
AppSec is being rewritten as code-review-with-security-context. The line between code review and SAST is dissolving.

- [[Snyk]] — $1.32B raised. Launched Evo agentic platform Oct 2025. Acquired Invariant Labs for AI security.
- [[Endor Labs]] — $93M Series B April 2025. 225% YoY growth. Reachability-based SCA.
- [[Apiiro]] — $135M total, $100M Series B in 2022. ASPM pioneer.
- [[DryRun Security]] — $8.7M seed Jan 2025. "Natural language code policies."

## Cross-cutting observations

**Open-source funnels work.** OpenRewrite, PR-Agent, GPT Pilot all converted GitHub stars into enterprise pipelines. The most defensible specialists ship an open-source primitive and sell the orchestration/scale layer.

**Managed services are back.** QA Wolf's per-test pricing and Antithesis's deterministic-simulation-as-a-service show buyers will pay for guaranteed outcomes, not just AI access.

**The MTTR/PR review categories will consolidate.** Eight code review tools and four+ SRE agents do not all survive. Expect 1-2 winners per slice in 24 months.

**Specialists eat into horizontal IDEs at the edges.** Why pay for Cursor's PR review when CodeRabbit is better at that one thing? The horizontal players will either build deep specialty modes or cede those revenue lines.

## See also
- [[Horizontal Coding Agents]] — Cursor, Windsurf, Cognition, Replit
- [[CLI Agents]] — Claude Code, OpenAI Codex CLI, Aider
- [[ADE Landscape Overview]]
