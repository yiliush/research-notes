---
tags: [tool, refactoring, migration, ai-agent, acquired, specialty-agent]
created: 2026-05-28
---

# Grit.io

Grit.io was the closest competitor to [[Moderne]] in the AI-assisted code migration space, with a more developer-friendly pattern DSL (GritQL) and a sharper focus on framework migrations. The company was acquired by Honeycomb in April 2025, ending its independent run. The acquisition was a soft exit — the team and tech became part of Honeycomb's observability stack rather than continuing as a standalone migration platform.

## Origin

Founded in 2022 by Morgante Pell, ex-Google software engineer. Grit emerged from Pell's frustration with the manual effort of large-scale codebase migrations. The pitch: "technical debt as a service" — Grit's agents continuously find and fix outdated patterns.

## Funding & Traction

- Total raised: ~$7M.
- Seed (Aug 2023): $7M led by Founders Fund and Abstract Ventures, with Quiet Capital, 8VC, A* Capital, AME Cloud Ventures, SV Angel, Operator Partners, CoFound Partners, Uncorrelated Ventures, plus angels Guillermo Rauch (Vercel), Scott Belsky (Adobe), Sahil Bloom.
- Acquired by Honeycomb.io in April 2025 (terms undisclosed).

## Product

- **GritQL**: declarative pattern language for code search and transformation. Comparable in spirit to OpenRewrite recipes but more concise and less Java-centric.
- **Grit Cloud**: managed service that runs GritQL patterns across an organization's repos.
- **AI-assisted migrations**: combined LLM intent inference with deterministic GritQL transforms.
- **Framework migrations** as canned products: React class-to-hooks, Next.js Pages-to-App router, Vue 2-to-3.

## Pricing (pre-acquisition)

- Free tier for small projects.
- Team and Enterprise plans, custom pricing.

## Differentiators

- **GritQL DSL.** More approachable than [[Moderne]]'s OpenRewrite recipes for non-Java teams.
- **TypeScript/JS-first.** Strongest in the JavaScript ecosystem where Moderne was weakest.
- **Acquired into Honeycomb** — the migration tech now powers Honeycomb's observability-to-code feedback loops.

## Risk factors / lessons

- The exit price was modest (not disclosed but signaled as a tuck-in, not a strategic acquisition).
- The lesson: standalone code migration is a hard standalone business. Margins are project-shaped, sales cycles long, and the work eventually ends. Moderne survived by going deep into enterprise Java compliance; Grit ran out of runway in JS.

## See also
- [[Moderne]]
- [[Second.dev]]
- [[Pythagora]]
- [[Specialty Agents]]
