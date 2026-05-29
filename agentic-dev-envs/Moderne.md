---
tags: [tool, refactoring, migration, enterprise, open-source, specialty-agent]
created: 2026-05-28
---

# Moderne

Moderne is the commercial company behind OpenRewrite, the deterministic refactoring engine that has quietly become the foundation layer underneath AWS Q Code Transformation, GitHub Copilot's Java upgrade assistant, and Broadcom's AI coding agents. While AI code-gen startups raise on token-burning demos, Moderne sells the boring-but-essential piece: a working compiler-grade IR that lets you safely rewrite millions of lines of enterprise Java.

## Origin

Founded by Jonathan Schneider (CEO) and Olga Kundzich, both ex-Pivotal (acquired by VMware for $2.7B in 2019). Before Pivotal, Schneider was at Netflix where he created Rewrite — an internal Java refactoring engine that became the basis of OpenRewrite. He open-sourced it at Netflix, then commercialized via Moderne starting 2021.

## Funding & Traction

- Total raised: ~$50M.
- Seed (July 2021): $4.7M.
- Series A (2023): $15M.
- Series B (Feb 2025): $30M led by Acrew Capital, with Allstate, Amex Ventures, Intel Capital, Mango Capital, Morgan Stanley, TIAA Ventures, True Ventures.
- Customer growth: 250% in 2024.
- OpenRewrite repo: ~3,400 stars on the main `openrewrite/rewrite`.

## Product

Two layers:

1. **OpenRewrite (OSS).** A type-aware compiler-grade IR (Lossless Semantic Tree) for source code. "Recipes" are programs that traverse this tree and emit changes. Supports Java, Kotlin, Groovy, Python, TypeScript, YAML, XML, properties, Gradle/Maven build files. Critically, it's deterministic — unlike LLM refactoring, the same recipe yields the same output every run.
2. **Moderne Platform.** Cloud/on-prem service that ingests an entire organization's codebases (often 1,000+ repos at a Fortune 500), runs recipes at scale, and produces auditable PRs. Adds AI agents on top for recipe authoring and impact analysis.

The combination is the moat: AI handles intent, OpenRewrite handles correctness.

## Pricing

- OpenRewrite OSS: free.
- Moderne Platform: enterprise contracts, typically six-figure annual.

## Differentiators

- **The platform that AI agents use.** AWS Q, GitHub Copilot upgrade assistant, and others embed OpenRewrite under the hood. Moderne is the Intel Inside of code modernization.
- **Deterministic correctness.** LLM refactoring is probabilistic; OpenRewrite recipes are auditable transformations.
- **Multi-repo scale.** Designed for orgs with thousands of repos, not single-repo dev tools.
- **Java/JVM heritage.** Stronger in enterprise Java than any LLM-first competitor.

## Notable customers

Walmart, Choice Hotels, Allstate, five of the top North American banks. AWS Q and GitHub Copilot integrations validate the engine technically.

## Risk factors

- LLM-only competitors are pushing the "you don't need a deterministic IR, just run the model" thesis. If model accuracy crosses a threshold, recipe authoring overhead may not justify the platform.
- OpenRewrite governance was criticized in 2025 by Jonathan Leitschuh ("When Open Source Isn't") for moving permissive code to commercial license — could affect OSS goodwill.
- [[Grit.io]] tried a similar pattern-based migration approach and was acquired (modestly) by Honeycomb.

## See also
- [[Grit.io]]
- [[Second.dev]]
- [[Snyk]]
- [[Specialty Agents]]
