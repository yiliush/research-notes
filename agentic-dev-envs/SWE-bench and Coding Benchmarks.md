---
tags: [infrastructure, concept]
created: 2026-05-28
---

# SWE-bench and Coding Benchmarks

Coding benchmarks are the public scoreboard of the ADE category. SWE-bench, in particular, became the headline number every model launch cites — and the most contested. By May 2026 the top score on SWE-bench Verified is ~94% (Claude Mythos Preview) and the saturation debate is acute. New, harder benchmarks (SWE-bench Pro, Terminal-Bench 2.0, SWE-Lancer) are filling the gap. This note catalogs the key benchmarks, their methodology, and current SOTA as of May 2026.

## SWE-bench (Princeton, 2023)

The original benchmark: 2,294 real GitHub issues from 12 popular Python repositories. Each task: given the issue text and the repo state, produce a patch that resolves the issue (passes the hidden tests). Tests are real maintainer tests, not synthetic.

Three subsets are in active use:
- **SWE-bench Full** — all 2,294 tasks. Saturating; rarely used as headline metric now.
- **SWE-bench Lite** — 300 task subset for cheap evaluation.
- **SWE-bench Verified** — 500 tasks human-verified for solvability. The current headline benchmark.

## SWE-bench Verified Leaderboard (May 2026)

| Model | Score | Notes |
|---|---|---|
| Claude Mythos Preview | 93.9% | Anthropic preview tier, May 22, 2026 |
| GPT-5.5 (OpenAI) | 88.7% | Released April 23, 2026 |
| Claude Opus 4.7 | 87.6% | |
| GPT-5.3-Codex | 85.0% | |

Top score jumped from ~65% in early 2025 to ~94% in May 2026. The benchmark is effectively saturating. Different leaderboards report slightly different numbers due to harness/scaffold differences — the "model + scaffold" pairing matters as much as the model.

## SWE-bench Pro (Scale AI, 2025)

A harder successor curated by Scale AI's labs. The 46% Pro score corresponds to roughly 81% on Verified, illustrating how much harder the curation is.

| Model | SWE-bench Pro |
|---|---|
| Claude Opus 4.7 | 64.3% |
| GPT-5.4 | 59.1% |
| GPT-5.3-Codex | 56.8% |

Pro is now the preferred frontier-model benchmark when Verified saturates.

## SWE-Lancer (OpenAI, Feb 2025)

1,488 freelance software engineering tasks from Upwork totaling $1M in real payouts. Two splits: independent contributor (IC) tasks ($50 bug fix → $32k feature) graded by triple-verified end-to-end tests, and SWE management decisions graded against the original engineering manager's choices.

Baseline scores (paper release):
- Claude 3.5 Sonnet: 26.2% IC, 44.9% Management, ~$400k total earnings.

By May 2026, frontier models pass higher absolute earnings but the benchmark remains far from saturated — published GPT-5.5 / Claude Mythos scores on SWE-Lancer are limited; OpenAI's reports describe it as "still the hardest of OpenAI's public engineering benchmarks." The structural difficulty is that the tasks require multi-file changes, infrastructure understanding, and dollars-per-bug economics no other benchmark replicates.

## Terminal-Bench (Stanford / Anthropic collaborators, 2024)

Tests an agent's ability to operate a Linux terminal — file operations, network tools, system administration, package management. Two versions in 2026:

**Terminal-Bench (original)** as of May 2026:
| Model | Score |
|---|---|
| Claude Sonnet 4.5 | 50.0% |
| MiniMax M2.1 | 47.9% |
| Kimi K2-Thinking-0905 | 47.1% |

**Terminal-Bench 2.0** (89-task harder set, designed for the 2026 frontier):
| Model | Score |
|---|---|
| GPT-5.5 | 82.7% |
| Claude Mythos Preview | 82.0% |
| GPT-5.3 Codex | 77.3% |

The average across all 40 evaluated models on T-Bench 2.0 is 56.9%. The gap between agents on the same model "shows how much scaffolding matters" — Terminal-Bench has become a popular harness benchmark.

**Terminal-Bench Hard** (curated subset by Artificial Analysis): GPT-5.5 (xhigh) leads at 60.6%.

## LiveCodeBench (UC Berkeley, ongoing)

Continuously sources fresh problems from LeetCode / AtCoder / CodeForces — designed to be contamination-free. Four scenarios: generation, self-repair, execution, test prediction.

May 2026 SOTA varies by source:
- Gemini 3 Pro Preview: 91.7%
- Gemini 3 Flash Preview: 90.8%
- DeepSeek V3.2 Speciale: 89.6%

Or, on a parallel leaderboard, DeepSeek-V4-Pro-Max at 93.5%, DeepSeek-V4-Flash-Max at 91.6%.

LiveCodeBench is the most trusted competitive-programming signal because its fresh problems avoid training contamination concerns.

## RepoBench (Tsinghua, 2023)

Repo-level code autocompletion. Tests cross-file context use for long-distance completions. Less talked-about in 2026 — partly because frontier models do this well, partly because newer benchmarks have absorbed the use case.

## MLE-bench (OpenAI, 2024)

Tests AI agents on real Kaggle ML competitions. Measures whether the agent can take a dataset + problem statement and produce a competition-grade ML solution. Frontier models trail strong human Kagglers but are closing the gap. Specialty benchmark for ML-focused coding agents.

## What the benchmarks miss

By mid-2026 the consensus critique:

1. **Saturation on SWE-bench Verified** makes it useless for differentiating top models. Pro and Lancer are partial replacements.
2. **Harness coupling** — a model's published score depends heavily on the scaffold (prompts, tools, retry logic). "Pure model" comparisons are rare and limited.
3. **No multi-day tasks.** All benchmarks are single-session. Real engineering work spans days. Devin's claimed strength is in this gap, but no public benchmark measures it well.
4. **No team-collaboration tasks.** Code review, PR negotiation, architecture discussions are absent.
5. **Limited language coverage.** Python dominates. JavaScript / TypeScript second. Rust, Go, C++, Swift are underrepresented relative to industry use.
6. **No long-tail repo coverage.** SWE-bench uses 12 popular Python repos; real enterprise code is messier.

The current frontier of benchmark work: long-horizon agent tasks (METR's HCAST, OSWorld), real-time interactive evals (DevAgent), enterprise-codebase evals (proprietary; e.g., what Cognition, Cursor, and OpenAI run internally and don't publish).

## See Also
- [[Agent Harness]]
- [[Codebase Indexing]]
- [[Competitive Dynamics]]
- [[Enterprise Adoption]]
