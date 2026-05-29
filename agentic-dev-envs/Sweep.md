---
tags: [company/sweepai, async-agent, autonomous-coding, pr-based, sweep, pivoted]
created: 2026-05-28
---

# Sweep

Sweep was one of the earliest production PR-based coding agents — a GitHub App that turned labeled issues into pull requests, predating Devin's viral moment by months. By 2025 the company pivoted away from the GitHub-Issue-to-PR agent toward an AI coding assistant and autocomplete for JetBrains IDEs. The original PR-bot lineage remains historically important for the cluster even though the product focus moved on.

## Background

- **Maker:** Sweep AI (sweepai/sweep on GitHub).
- **Founded:** 2023, San Francisco. YC-backed (W23).
- **Original product:** GitHub App. User labels an issue (e.g. `sweep:`) → Sweep analyzes the repo, generates a plan, edits files, opens a PR.
- **2025 pivot:** Team decided to refocus on a JetBrains IDE plugin with next-edit autocomplete and an AI coding assistant. The GitHub PR agent is no longer the company's primary product.
- **Why this matters for the cluster:** Sweep is the "PR-first agent" archetype that informed the Copilot coding agent and Jules' PR-output model.

## Funding & Traction

- **Y Combinator:** Winter 2023 batch.
- **Seed round:** Funding details not extensively disclosed publicly; standard YC seed-stage profile.
- **GitHub repo:** Active commits through 2025; recent issues span June–December 2025.
- **JetBrains plugin:** Available at plugins.jetbrains.com/plugin/26275-sweep-ai. Pitched as the only AI assistant supporting next-edit autocomplete in JetBrains IDEs at launch.

## Architecture (original PR-based product)

- **Trigger:** GitHub issue with a `sweep:` label or specific keyword.
- **Loop:** Sweep reads the issue → indexes the repo (vector + AST search) → generates a multi-step plan → creates a branch, edits files, commits → opens a PR for review → iterates on review comments.
- **Sandbox:** Cloud execution per task.
- **Model backbone:** Frontier models (Anthropic Claude family historically prominent).
- **SWE-bench:** No leading published SWE-bench Verified number; Sweep wasn't optimized for the benchmark task profile.

## Architecture (current JetBrains product)

- **IDE plugin** rather than cloud agent.
- **Next-edit autocomplete** as the headline feature — predicting the developer's next cursor move + edit.
- **Sync, not async.** This is no longer in the async-agent cluster — it's a copilot-style assistant.

## Pricing / Access

- **Original GitHub agent:** Free trial + paid plans on the GitHub Marketplace.
- **JetBrains plugin:** Plugin-marketplace distribution; pricing per the JetBrains plugin page.

## Differentiators

- **PR-first archetype.** Sweep was an early proof that the GitHub Issue → PR loop could be productized. That pattern is now the dominant interaction model for the cluster (Copilot agent, Jules, Devin).
- **YC pedigree + early shipping.** Production GitHub App in 2023, well before the cluster's 2024 explosion.
- **Pivot signal.** The pivot to JetBrains autocomplete is a real signal about the PR-bot market — Sweep's team concluded that solo PR-bot vendors couldn't beat GitHub-native and frontier-lab-native agents (Copilot agent, Jules). Net new entrants in the PR-bot space should weigh that conclusion.

## See Also

- [[Autonomous Coding Agents]]
- [[GitHub Copilot Workspace]] — the GitHub-native successor pattern
- [[Devin]]
- [[OpenHands]]
