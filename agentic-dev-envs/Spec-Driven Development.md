---
tags: [concept, spec-driven, sdd, methodology, ade-cluster, anti-vibe]
created: 2026-05-28
---

# Spec-Driven Development

Spec-Driven Development (SDD) is the practice of treating an executable,
version-controlled specification — not the source code — as the single source
of truth for a software system. The team (or an AI agent) first writes a
detailed spec describing what the system does, derives a technical plan,
breaks it into tasks, and only then generates code. When requirements change,
the spec changes and the code is regenerated. SDD emerged in 2025 as the
deliberate, structural answer to the failure mode of [[Vibe Coding]].

## The Thesis

> Specifications don't serve code — code serves specifications.

SDD inverts the traditional relationship between intent and implementation.
Instead of writing code and reconstructing intent from it later, SDD insists
that intent is captured first — completely, unambiguously, and in a form that
outlives any individual codebase. Code is the disposable artifact; the spec
is what you maintain.

The diagnostic claim underneath: the buggy, drift-prone output of [[Vibe Coding]]
is not a model-quality problem. It is a requirements problem. LLMs that hallucinate
APIs and accumulate stylistic incoherence are responding to underspecified prompts.
Give them a real spec and the output stabilizes.

## What A Spec Contains

A canonical SDD specification defines six elements:

1. **Outcomes** — what success looks like, behaviorally
2. **Scope boundaries** — what is and isn't part of this change
3. **Constraints** — technology, performance, compliance, prior decisions
4. **Prior decisions** — architectural choices already locked in
5. **Task breakdown** — atomic, reviewable units of work
6. **Verification criteria** — how you know the spec was satisfied

External behavior is described precisely: input/output mappings, pre- and
postconditions, invariants, integration contracts, state-machine logic.
[[Kiro]] uses EARS notation ("WHEN [condition] THE SYSTEM SHALL [behavior]")
to enforce precision.

## The 2025–2026 Movement

By mid-2026 every major AI coding tool had shipped a flavor of SDD:

- **[[GitHub Spec Kit]]** (September 2025) — the open methodology, 30+ agent integrations
- **[[Kiro]]** (AWS, July 2025 preview / November 2025 GA) — spec-first as the default IDE mode
- **[[Tessl]]** — the independent that has been arguing this since 2024; the early champion
- **[[Claude Code]]** — plan-mode / plan-then-execute is a partial SDD pattern
- **[[Cursor]]** — added spec workflows in late 2025
- **[[Antigravity]]** — Artifacts (plans, diffs, recordings) are SDD-adjacent: the spec-shaped evidence the agent produces
- **OpenSpec, BMAD** — adjacent open-source frameworks

Signal of mainstream crossover: DeepLearning.AI launched a dedicated
"Spec-Driven Development with Coding Agents" short course in late 2025.
Thoughtworks named SDD one of 2025's defining engineering practices.

## Contrast With Vibe Coding

| | [[Vibe Coding]] | Spec-Driven Development |
|---|---|---|
| Primary artifact | The running app | The specification |
| Operator's job | Describe intent, accept output | Write the spec, review the plan |
| Failure mode | Drift, hallucination, decay | Spec rot, upfront overhead |
| Suitable for | Prototypes, weekend builds | Production systems, regulated work |
| Champion | Karpathy (Feb 2025) | Tessl, GitHub, AWS (2025) |

The two are not opposites so much as endpoints. Most real workflows in 2026
land somewhere on the spectrum — prompt-driven for exploration, spec-driven
for anything that has to survive a maintenance cycle.

## Critique

- **Spec rot is the same problem under a different name.** If teams don't
  maintain the spec, it drifts from the code and the inversion is lost.
- **The upfront cost is real.** SDD trades faster iteration for fewer rewrites.
  For genuinely throwaway work, that trade is wrong.
- **Spec-as-source-of-truth is an old idea.** Formal methods, contract-first
  APIs, BDD all pre-date SDD. The new variable is that LLMs can now consume
  the spec and generate code from it, which is what makes the round-trip cheap
  enough to be practical. The methodology is older than the tooling.

## See Also

- [[Vibe Coding]] — the contrasting end of the spectrum
- [[GitHub Spec Kit]] — the open reference implementation
- [[Kiro]] — the productized hyperscaler version
- [[Tessl]] — the independent champion
- [[AGENTS.md Standard]] — adjacent standard at the operational-context layer
- [[Agent Harness]]
- [[Autonomous Coding Agents]]
