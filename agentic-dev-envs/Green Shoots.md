---
tags: [cluster-index, open-source, scrappy, early-stage, ade-cluster]
created: 2026-05-28
---

# Green Shoots

Cluster note for the early-stage, pre-traction, easy-to-miss OSS and scrappy projects in the ADE category. These are projects that don't show up on the first three pages of a Google search for "AI coding tool" but are where the next category leaders might emerge. The pattern across this cluster: small or solo teams, GitHub-first distribution, non-obvious differentiators, often archived or paused but with intact codebases ready to be picked up.

## Why This Cluster Matters
The visible market is dominated by funded plays: [[Cursor]], [[Windsurf]], [[GitHub Copilot]], [[Claude Code]], [[Codex CLI]], [[Devin]]. The conventional wisdom is that the category leaders are set. But:

1. Several "scrappy" projects have star counts that rival or exceed funded competitors (e.g. [[Open Interpreter]] at 63.7k > [[Cursor]]'s public repo would have if it were OSS).
2. Architectural innovations frequently originate at the edges (Aider's repo-map, Open Interpreter's local code execution, smolagents' code-as-action, Aide's separable agent harness).
3. Paused or archived projects with strong stars are takeover candidates — Void, Aide, Bloop, and Plandex all sit on intact codebases with engaged communities.

## Members

### Scrappy OSS coding agents
- [[Plandex]] — Go-based terminal agent; ~15.4k stars; cloud winding down, self-hosted continues
- [[Open Interpreter]] — Killian Lucas's "natural language interface for computers"; ~63.7k stars
- [[smolagents]] — Hugging Face's 1,000-line code-action agent library; ~27.6k stars
- [[Mentat]] — biobootloader's terminal agent → MentatBot GitHub bot pivot
- [[Backlog.md]] — markdown-as-task-queue orchestrator
- [[Charlie Labs]] — "Charlie" the AI on-call engineer
- [[Pythagora]] — GPT Pilot's OSS IDE

### OSS / scrappy AI IDEs
- [[Pear AI]] — YC-backed Continue fork with rocky launch; ~690 stars
- [[Void]] — YC-backed OSS Cursor alt; ~28.8k stars; dev paused
- [[Aide]] — CodeStory's archived AGPL VS Code fork; ~2.2k stars
- [[CodeStory]] — Aide's parent company; pivoted upstream

### Code intelligence substrate
- [[Sourcegraph]] — incumbent code search, distinct from Cody/Amp
- [[Greptile]] — agent-substrate code indexing
- [[Bloop]] — Rust code search, pivoted to agent orchestration

## Pattern Observations

**Cloud wind-downs without project death.** Plandex, Bloop, Void, and Aide all show the same shape: small teams hit infrastructure cost limits or pivot opportunities, the hosted product winds down, the OSS code persists. The signal is that hosting an OSS coding agent at scale is brutal unit economics.

**Star counts don't predict revenue.** Open Interpreter has 63.7k stars and no commercial product. Mentat had a CLI with 2.6k stars and a viable GitHub-bot business. Cursor has no public OSS repo and $2B ARR. Star counts measure developer mindshare, not willingness to pay.

**Code-as-action is winning the framework debate.** smolagents, Open Interpreter, and Claude Code all favor letting the agent write executable code over JSON tool calls. This was a contested design point in 2023; by mid-2026 it's the consensus.

**The "OSS Cursor" category is fragmented.** Continue (extension), Void (fork, paused), Aide (fork, archived), Pear AI (fork, controversy), Cline (extension), Roo Code (extension), Kilo Code (extension). No clear winner. Continue has the highest enterprise pull; Void has the highest community stars among forks. The category may not consolidate until Microsoft picks a horse for VS Code itself.

## Surprises and Contradictions to Conventional Wisdom

- **Open Interpreter is enormous.** 63.7k stars puts it in the top tier of any AI project. It's underdiscussed in ADE coverage because it's framed as "personal computing" rather than "coding," but architecturally it's an ancestor of every code-execution agent that came after.
- **Aide was first to ship the separable-agent-binary architecture** that Claude Code and Codex CLI later popularized. Its archival was strategic retreat, not technical failure.
- **Bloop's pivot is undervalued.** A team with deep Rust + search infrastructure experience moving into agent orchestration is a stronger bet than the public narrative suggests.
- **Plandex's wind-down is a category warning.** A 15k-star OSS project with a single committed maintainer couldn't keep up with Anthropic and OpenAI shipping their own CLI agents for free. This is the canary for any indie OSS agent project.
- **Pear AI's reputational damage is real and persistent.** The September 2024 plagiarism controversy is still the first result for "PearAI" searches in May 2026, two years later. YC's willingness to back it cost YC reputation in the OSS community.
- **smolagents' growth is the quiet story.** 3k → 27.6k stars in 18 months while staying ~1,000 LOC is exceptional discipline.

## See Also
- [[AI-Native IDEs]] — adjacent cluster
- [[CLI Coding Agents]] — adjacent cluster
- [[Autonomous Coding Agents]] — adjacent cluster
- [[Parallel Agent Orchestrators]] — adjacent cluster
- [[Market Landscape]]
- [[Market Structure and Value Chain]]
