---
tags: [vibe-coding, spec-driven, ai-native, tessl, ade]
created: 2026-05-28
---

# Tessl

Tessl is the spec-driven outlier in this cluster. Founded by Snyk's
Guy Podjarny, it argues that the artifact developers should maintain is
not source code but a specification, with agents regenerating code as
needed. Tessl shipped its first products in 2026 after an unusually
quiet, well-funded gestation.

## Origin

Founded by Guy Podjarny (founder of Snyk). Operates from London. The
thesis: when AI can write code reliably, the moat moves to *what to
build*. Specs become the long-term memory of a system; code becomes
ephemeral output.

## Funding & Traction

- Seed: $25M in April 2024, led by boldstart and GV
- Series A: $100M, led by Index, with Accel participating
- Total raised: $125M
- Post-money valuation reported at $750M (Yahoo Finance / Crunchbase)
- Stealth through most of 2024-2025; first products shipped in 2026

## Product

Tessl's launch products (2026) are explicitly a framework, not a
prompt-to-app builder in the Lovable/Bolt sense:

- **Tessl Framework**: keeps agents "on rails" using specifications.
  Specs are stored in the codebase as long-term memory. Supports both
  hand-crafted specs and AI-generated "vibe-spec" workflows. Generates
  tests to enforce that agents do not break existing functionality.
- **Tessl Spec Registry**: a public registry holding 10,000+ specs for
  external libraries (Express, React, Stripe, etc.). Agents consult the
  registry to avoid API hallucination and version mixing.

March 2026 release added global installs, watch mode, GitHub badges,
and a unified score.

## Pricing (May 2026)

Tessl has not published standard SaaS pricing tiers. The framework is
available as open developer tooling; the registry is free to read. The
revenue model points toward enterprise contracts for governance,
private registries, and agent enablement at scale rather than per-seat
SaaS.

## Differentiators

- **Spec-driven, not vibe.** Tessl is in this cluster by adjacency, not
  by category. It is what some Lovable/Bolt users discover they wanted
  once they hit the maintainability wall.
- **Aimed at professional developers**, not non-engineers. The framework
  assumes the user understands what a spec is and reads the tests.
- **Registry as moat.** A curated, versioned set of specs for the open
  source ecosystem is hard to recreate and benefits from network effects
  as more agents consume it.
- **The maintainability answer.** If the "vibe coding tax" is the long-
  term liability of unreadable AI-generated code, Tessl's claim is that
  specs are the asset that survives model upgrades, refactors, and
  rewrites. See [[Vibe Coding]].

## See Also

- [[Vibe Coding]]
- [[Vibe Coding Platforms]]
- [[Bolt.new]]
- [[Replit Agent]]
