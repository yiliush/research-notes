---
tags: [tool, code-search, pivoted, archived, ade-cluster]
created: 2026-05-28
---

# Bloop

Bloop was a London-based, Rust-built code search engine — "ChatGPT for your code" — that launched in 2023 as one of the earliest AI-on-codebase products. The original Rust OSS search engine was archived January 2025. The company pivoted to AI agent orchestration: planning, dispatching, and reviewing the work of autonomous coding agents. By May 2026 the original Bloop is dead as a product, but the team is alive, building something new in a much hotter category.

## Origin
- Founded London (~2022) by ex-Palantir engineers. Seed funding from undisclosed investors.
- Original product: local code search using Tree-sitter, Tantivy, and Qdrant; semantic search with on-device embeddings (privacy-first). Distributed as a Tauri desktop app.
- Open-sourced the core search engine. AGPL/proprietary mixed.

## Adoption (original search product)
- GitHub stars verified May 2026: ~9.5k on `BloopAI/bloop`. Repo archived January 2, 2025.
- Last release: v0.6.5 in April 2024.
- Real user base was modest — code search alone was a thin product once Cursor/Continue/Cody bundled it for free.

## The Pivot
- Late 2024 / early 2025: Bloop announced it was building "tools that enable you to plan, orchestrate and review the work of autonomous AI agents."
- Current positioning (bloop.ai): an engineering workflow platform that lets engineers "operate more like high-velocity engineering managers while agents handle more of the implementation grind."
- Specific product details thin in public materials — looks like late-stage closed beta as of May 2026.

## Architecture (new direction, from public-facing materials)
- Plan-first workflow: humans specify the unit of work, the platform dispatches agents.
- Review-centric: emphasis on the human-review surface for AI-generated changes.
- Implied multi-agent / fleet semantics.
- No public OSS components in the new product.

## Differentiators
- Team has unusual depth on Rust and search infrastructure — that capability transfers if the new product depends on indexing and retrieval at scale, which agent orchestration likely does.
- "Plan + orchestrate + review" framing puts Bloop directly into the lane occupied by [[Conductor]], [[Magnet]], [[Agent Farm]], [[Claude Squad]], and [[uzi]] — a crowded space.

## Strategic Position
- Original code search was eaten by the IDEs that bundled indexing for free. Pivoting was the right call.
- New direction is in a category that hasn't crowned a winner yet, but Bloop is a late entrant — Conductor, Magnet, and the "parallel agent" cluster have been shipping into it since mid-2024.
- The team's London-AGPL-Rust pedigree is interesting but not obviously a moat in an orchestration product where UX and ecosystem integrations matter more than core perf.

## See Also
- [[Sourcegraph]] — the code-search incumbent that survived
- [[Greptile]] — pure-play code-search-for-agents
- [[Conductor]] — orchestrator competitor
- [[Magnet]] — orchestrator competitor
- [[Parallel Agent Orchestrators]]
- [[Green Shoots]]
