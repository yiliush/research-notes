---
tags: [concept, fundamental]
created: 2026-05-28
---

# Inner Loop vs Outer Loop

The single most useful frame for understanding why the ADE market split the way it did. **Inner loop** is the seconds-to-minutes feedback cycle a developer experiences while typing — autocomplete, inline edits, instant tests. **Outer loop** is the minutes-to-hours cycle around a unit of work — issue triage, PR generation, code review, merge, deploy, post-deploy debugging. Different vendors are betting on different loops, and that bet determines almost everything about their product.

## The Distinction

| Dimension | Inner Loop | Outer Loop |
|---|---|---|
| Time horizon | Sub-second to minutes | Minutes to hours (sometimes days) |
| Human role | In-the-seat, attending to every keystroke | Reviewer / delegator / dispatcher |
| Surface | IDE / terminal / autocomplete | PR / issue / Slack / ticket |
| Latency budget | Tight — has to feel instant | Loose — async is fine |
| Failure cost | Annoying but recoverable in seconds | Wasted hours; sometimes wasted PR review cycles |
| Defensibility | Editor surface, autocomplete model, indexing | Workflow integrations (GitHub, Jira, Slack), task quality |

## Who's Where

**Pure inner loop:** Cursor's tab completion, Copilot's ghost text, Continue's autocomplete, JetBrains AI's line completion, Tabnine.

**Inner loop + agent panel:** Cursor's Composer, Windsurf's Cascade, Cline, Roo Code, Claude Code (terminal-bound but still inner loop in spirit). Developer drives the loop turn by turn.

**Outer loop:** [[Devin]], [[Jules]], [[Codex Cloud]], [[Factory.ai Droids]], [[GitHub Copilot Workspace]], [[OpenHands]] cloud. Developer hands off, reviews PR later.

**Specialty outer loop:** [[CodeRabbit]] (review), [[Greptile]] (review), [[Resolve.ai]] (on-call), [[Mintlify]] (docs), [[Tusk]] (testing).

## Why the Frame Matters

- **Inner-loop vendors compete on UX** (latency, indexing freshness, autocomplete quality, model integration). Cursor's $50B valuation is an inner-loop valuation — they own seconds of every developer's day.
- **Outer-loop vendors compete on autonomy and trust** (SWE-bench Verified, low false-merge rate, audit trails, enterprise reviewability). Cognition's $10B+ valuation is an outer-loop bet — Devin is sold as a developer-replacement at the task level.
- **Vibe-coding ([[Vibe Coding]]) is structurally outer-loop** sold to non-engineers — Lovable's user never sees the inner loop.

## Convergence Pressure

Every major vendor is trying to span both loops:
- Cursor added Background Agents (outer loop) on top of inline edits (inner loop)
- Devin added Devin IDE — an inner-loop surface bolted to its async agent
- Claude Code added background tasks; Codex CLI added cloud delegation
- Copilot has both Tab + Agent Mode and Copilot Workspace

The frame still holds because the **economics differ**: inner loop pays per seat (predictable, sticky), outer loop pays per task (volatile, big TAM, harder to underwrite).

## The Deep Reason for the Split

Engineering work is bimodal. Some work is "thinking-with-the-keyboard" — debugging, refactoring under live constraints, exploring an unfamiliar codebase. Some work is "specification work" — clear requirements, clear acceptance criteria, repeatable patterns. Inner-loop agents serve the first mode; outer-loop agents serve the second. No vendor has convincingly served both with one surface.

## See Also
- [[Agent Harness]]
- [[Autonomous Coding Agents]]
- [[Vibe Coding]]
- [[Long-Horizon Coding]]
- [[Background Agents]]
- [[Market Structure and Value Chain]]
