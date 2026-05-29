---
tags: [vibe-coding, browser-based, prompt-to-ui, design-tool, ycombinator, ade]
created: 2026-05-28
---

# Magic Patterns

Magic Patterns is a Y Combinator-backed AI prototype generator for
product teams. It is the v0 alternative aimed at designers and PMs who
want to ship prototypes that match an existing design system, rather
than generic shadcn-flavoured UI.

## Origin

Founded as a Y Combinator company focused on AI UI generation. The
product positioning is narrower than Lovable or Bolt — Magic Patterns
explicitly markets itself as a *prototype* generator for product teams,
not a "ship the whole app" tool. The pitch: turn text prompts or
screenshots into editable components and screens that look like your
existing product.

## Funding & Traction

- YC-backed; specific round amounts not publicly disclosed
- 100,000+ components generated through community use
- No public ARR disclosure

## Product

You input a text prompt or upload a screenshot. Magic Patterns generates
editable UI components and screens. The differentiating capability is
custom design system support: paid tiers let you load your team's
existing components and Tailwind tokens so the generated UI matches.

**Generated stack**: React + Tailwind. Production-quality component
output meant for paste-in to an existing codebase, not a standalone
runtime.

**Deployment**: Less of a deploy story than Bolt/Lovable. Magic Patterns
is primarily a generator that emits code into your real repository.

## Pricing (May 2026)

| Tier | Price | Credits / use |
|------|-------|---------------|
| Free | $0 | basic generation |
| Hobby | $19/seat/mo | 100 monthly credits, rollover, private, no training, custom domains, faster model |
| Starter | $20/mo | individual paid tier |
| Pro | $75/seat/mo | 350 credits, custom design systems, shared styles, shared component library, Slack Connect |
| Business | $100/mo | team features |
| Enterprise | custom | volume |

15% off with annual billing.

## Differentiators

- **Bring your own design system.** The Pro tier is the standout
  feature: Magic Patterns will conform to your library and tokens. v0
  output looks like every other v0 output. Magic Patterns output looks
  like your product.
- **Screenshot input.** Visual reference as a first-class prompt input,
  not just text.
- **Prototype-first.** Lower implicit scope means cleaner output for the
  use case. Magic Patterns does not pretend to be a deployment platform.
- **Team workflow.** Slack Connect, shared libraries, and shared styles
  signal a product team orientation rather than indie hacker.

## See Also

- [[Vibe Coding Platforms]]
- [[Vibe Coding]]
- [[v0]]
- [[Tempo Labs]]
