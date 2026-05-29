---
tags: [tool, repo-intelligence, code-search, ai-agent, specialty-agent]
created: 2026-05-28
---

# Sourcegraph

Sourcegraph is the godfather of code search — a category they essentially defined over a decade — and the most awkward incumbent in the ADE landscape. Founded in 2013, with $300M+ raised at a $2.62B peak valuation in 2021, the company has had to navigate the AI transition harder than almost any other developer tools company. In 2025 they sunset their Cody Free and Pro plans and launched a new agent, Amp, signaling a strategic reset.

## Origin

Founded in 2013 by Quinn Slack and Beyang Liu. Built code search as a primitive — "Google for your codebase" — and shipped a powerful intelligence layer (definitions, references, cross-repo search) that many large engineering orgs adopted.

## Funding & Traction

- Total raised: ~$300M.
- Series D (Aug 2021): $150M at $2.62B valuation, led by Andreessen Horowitz and Sequoia.
- No major funding round since 2021 — the AI transition has been navigated on existing capital.
- 2,000+ enterprise customers historically including Uber, Lyft, GE, Indeed, F500 banks.

## Product

Three layers:

1. **Code Search & Intelligence.** The original product — universal code search across repositories with definitions/references/git-blame. Still differentiated for enterprise scale.
2. **Cody (now Enterprise-only).** AI coding assistant, IDE-integrated. As of July 2025, Sourcegraph discontinued the Free, Pro, and Enterprise Starter tiers — Cody is now only available bundled with the Enterprise plan.
3. **Amp.** A new AI coding agent launched in 2025, positioned as Sourcegraph's answer to Cursor and Claude Code. Built on the code search index as context.

## Pricing

- Code Search Enterprise: custom.
- Cody / Amp: bundled with Enterprise; no self-serve tier as of 2025.

## Differentiators

- **The deepest code index in the market.** A decade of engineering on the search/intelligence layer.
- **Enterprise distribution.** F500 engineering orgs already use Sourcegraph for search; AI features can be sold into the same accounts.
- **Self-hostable.** Critical for regulated industries.

## Risk factors

- AI coding assistants commoditized faster than Sourcegraph could capture the seat economics — hence the 2025 tier sunset.
- [[Greptile]] is doing newer-stack code intelligence with sharper focus.
- Horizontal agents (Cursor, Claude Code, Codex) bypass Sourcegraph's search layer by indexing per-session.
- No new funding signal in 4+ years raises questions about runway/strategy.

## See also
- [[Greptile]]
- [[Unblocked]]
- [[CodeStory]]
- [[Specialty Agents]]
