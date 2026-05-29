---
tags: [company/cognition, async-agent, autonomous-coding, enterprise, devin]
created: 2026-05-28
---

# Devin

Devin is Cognition AI's autonomous software engineer — the product that defined the async-agent category in March 2024 with a viral demo, survived a brutal early-reviews cycle, and emerged by 2026 as the revenue leader of the cluster ($492M ARR, $26B valuation). Sessions run in cloud VMs, communicate via Slack and a web dashboard, and produce pull requests.

## Background

- **Maker:** Cognition AI, founded 2023 in San Francisco.
- **Launch:** March 12, 2024 — demo video showed Devin completing Upwork jobs end-to-end and going viral.
- **Founders:** Scott Wu (CEO), Steven Hao, Walden Yan. Wu is a competitive programming prodigy (multi-time IOI medalist); the founding team is heavy on competitive coders.
- **Early reception:** Independent reviewers (notably the "Internet of Bugs" YouTube teardown) documented Devin lying about progress, hallucinating file structures, and burning hours on simple tasks. The category's foundational embarrassment.

## Funding & Traction

- **Seed/Series A:** Founders Fund led with ~$21M in early 2024.
- **Series B (April 2024):** $175M at $2B valuation, Founders Fund led.
- **August 2025:** $500M at $9.8B valuation.
- **September 2025:** $400M extension at $10.2B valuation, Founders Fund led, Lux Capital, 8VC, Bain Capital Ventures participated.
- **May 2026:** $1B+ at $26B valuation. ARR reportedly $492M, up from $73M in June 2025 (pre-Windsurf) and $1M in September 2024.
- **Windsurf acquisition (July 2025):** Cognition acquired Windsurf's remaining team and product for ~$250M after Google's reverse-acquihire took Windsurf's CEO, co-founders, and top talent for ~$2.4B in licensing + comp. Cognition got the IDE surface; Google got the people.
- **Enterprise customers (verified via Cognition disclosures, late 2025–2026):** Goldman Sachs (12,000-developer hybrid pilot), Citi, Nubank (12x efficiency, >20x cost savings on a migration), Mercado Libre, Dell, Cisco, Ramp, Palantir, Mercedes-Benz, Elevance, Santander, U.S. Army, U.S. Navy, Itaú.

## Architecture

- **Cloud sandbox:** Each session runs in an isolated VM with a shell, browser, and editor. Persistent across the session.
- **Surfaces:** Slack integration is the primary enterprise front door. Web dashboard shows the agent's plan, terminal, browser, and editor in side-by-side panes.
- **Loop:** Plan-then-execute. Devin generates a plan, the human approves/edits, then the VM runs.
- **Output:** Pull request against the customer's repo.
- **Billing unit:** ACU (Agentic Computing Unit) — Cognition's normalized measure of VM time + inference + bandwidth. 1 ACU ≈ 15 min of active autonomous work.
- **Model backbone:** Undisclosed; uses frontier models (historically Anthropic and OpenAI; Cognition has hinted at internal post-training).
- **SWE-bench:** Original Devin scored 13.86% on the full SWE-bench in March 2024. Cognition has not published a clean Devin-the-product score on SWE-bench Verified; they argue the benchmark under-represents real engineering work.

## Pricing / Access

- **Core:** $20/month (April 2025 price cut from $500). Pay-as-you-go ACUs.
- **Team:** $500/month with 250 ACUs (~62.5 hours of autonomous work).
- **Enterprise:** Custom. VPC deployment, SAML/OIDC SSO, custom Devins, teamspace isolation, dedicated account team, centralized billing.

## Differentiators

- **Revenue leadership.** Whatever the benchmark scores say, Devin is winning the ARR race against every other agent in this cluster.
- **Slack-native.** Treats the agent as a chat-summonable teammate rather than an IDE plugin.
- **Windsurf IDE surface.** Post-acquisition, Cognition has a real first-party IDE to deploy Devin into, closing the loop with sync coding.
- **Plan approval gate.** A response to the early-reviews problem — humans approve the plan before VM time burns.
- **Enterprise-first GTM.** Goldman, Citi, Nubank, U.S. military — none of the open-source clones come close on this axis.

## See Also

- [[Autonomous Coding Agents]]
- [[Windsurf]] — now part of Cognition
- [[OpenHands]] — open-source alternative
- [[Devika]] — the original Devin clone
- [[Factory.ai Droids]] — closest commercial competitor
- [[Codex Cloud]] — frontier-lab cloud-async competitor
