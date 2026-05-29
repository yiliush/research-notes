---
tags: [tool, github, spec-kit, spec-driven, open-source, ade-cluster]
created: 2026-05-28
---

# GitHub Spec Kit

GitHub Spec Kit is the open-source toolkit GitHub released in September 2025 to popularize [[Spec-Driven Development]] as a practice. It packages templates, a CLI, and a four-phase workflow (`/specify` → `/plan` → `/tasks` → `/implement`) that any compatible AI agent can drive. It is the GitHub-blessed, vendor-neutral methodology answer to the failure mode of [[Vibe Coding]] — and the open counterpart to [[Kiro]]'s product-shaped take on the same thesis.

## Release and Position

- **Released September 2025** on `github.com/github/spec-kit`, MIT-licensed.
- Maintained as a methodology + tooling toolkit, not a hosted product. Distribution is the CLI, templates, and the `spec-driven.md` philosophy doc.
- Supports 30+ AI-agent integrations as of May 2026: [[GitHub Copilot]], [[Gemini CLI]], Codex, [[Windsurf]], [[Claude Code]], Forge, [[Kiro]], and more. Switching agents is a single CLI flag — no lock-in.

## The Workflow

Four gated phases with explicit checkpoints between each:

1. **Specify** — `/specify <feature description>`. Generates the specification: goals, user journeys, scope boundaries. The "what."
2. **Plan** — `/plan`. Produces the technical plan: architecture, stack, constraints, prior decisions. The "how."
3. **Tasks** — `/tasks`. Decomposes the plan into small, individually-reviewable, testable work units.
4. **Implement** — `/implement`. The agent executes tasks one at a time, with validation between each.

Each phase requires human review before advancing. The spec is version-controlled; code is regenerable from it.

## Core Thesis

From the project's `spec-driven.md`:

> Specifications don't serve code — code serves specifications.

The methodology inverts the traditional relationship between intent and implementation. The spec is the durable artifact; code is the disposable output. When requirements change, you edit the spec and regenerate, rather than refactoring the code and hoping the spec catches up.

## Use Cases GitHub Highlights

- **Greenfield projects**: spec captures the "what" before any code exists.
- **Feature work in existing systems**: spec scopes the change against the existing architecture.
- **Legacy modernization**: spec describes the target behavior, agent generates the migration plan.

GitHub claims teams using Spec Kit internally ship features with roughly an order of magnitude fewer "regenerate from scratch" cycles than ad-hoc prompting.

## Strategic Position

- Spec Kit is GitHub's methodology bet without committing to a product. Unlike [[Kiro]], Spec Kit is not an IDE — it slots into whatever IDE/agent the team uses. This is consistent with GitHub's platform-not-product posture in AI coding (Copilot inside VS Code, not a separate IDE).
- It validated spec-driven development as a category. By late 2025, every major agentic tool ([[Kiro]], [[Claude Code]], [[Cursor]], [[Antigravity]], [[Tessl]]) had shipped some flavor of SDD. Spec Kit is the open reference implementation that lowered the cost of trying the idea.
- The 30-agent integration list is the strategic moat: it positions Spec Kit as the connective tissue across the agent ecosystem, which is the same play [[AGENTS.md Standard]] makes for context files.
- DeepLearning.AI launched a "Spec-Driven Development with Coding Agents" short course in late 2025 using Spec Kit as the reference — a signal the methodology has crossed from experimental to mainstream.

## See Also

- [[Spec-Driven Development]] — the concept Spec Kit operationalizes
- [[Kiro]] — the productized counterpart
- [[Tessl]] — the spec-first independent
- [[AGENTS.md Standard]] — sibling open standard at a different layer
- [[Vibe Coding]] — the failure mode SDD is positioned against
- [[GitHub Copilot]]
