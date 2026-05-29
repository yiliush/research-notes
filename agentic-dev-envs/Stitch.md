---
tags: [company, google, stitch, design-to-code, ai-ui]
created: 2026-05-28
---

# Stitch

Stitch is Google Labs' AI design-to-code product, launched at Google I/O in May 2025. It generates mobile and web UIs from text prompts, image uploads, and annotated screenshots, then exports production-ready code across seven frameworks. It sits in the design-handoff niche where [[v0]], [[Magic Patterns]], and Figma's AI features compete — not a full IDE, but the part of the agentic-dev stack that converts intent into rendered UI plus working code.

## Product

- Text-to-UI and image-to-UI generation, powered by Gemini (Gemini 2.5 Flash/Pro at launch; Gemini 3.0 Flash/Pro from March 2026).
- 5-screen canvas: generate up to five interconnected screens simultaneously and auto-map user journeys. Click "Play" to walk the interactive flow.
- Auto-next-screen generation: Stitch can derive the next logical screen from a click in the previous one, building out flows iteratively.
- Code export targets: HTML/CSS, Tailwind, Vue, Angular, Flutter, SwiftUI, and React/JSX — seven frameworks as of the March 2026 expansion.
- Hosted at `stitch.withgoogle.com`. Pairs with Google AI Studio for the design-to-deploy workflow.

## Pricing

Free Google Labs experiment with monthly generation quotas (as of April 2026):
- 350 standard generations (Gemini 3.0 Flash or 2.5 Flash)
- 200 experimental/Pro generations (Gemini 3.0 Pro or 2.5 Pro)
- Total: 550 generations/month

No paid tier yet — Stitch remains a Labs surface for distributing Gemini's multimodal UI capabilities rather than a revenue product.

## Strategic Position

- Stitch is Google's wedge into the design-to-code segment that Figma, [[v0]], and the vibe-coding platforms ([[Lovable]], [[Bolt.new]]) compete for. The differentiator is Gemini's multimodal grounding — image inputs feed into the same model that generates the code.
- Adjacent to [[Antigravity]] in Google's developer-AI stack: Stitch produces the front-end artifact; Antigravity is where you take it to build the rest of the system. Google has not (as of May 2026) merged them, but the design-to-IDE handoff is the obvious roadmap item.
- Strategically a Labs experiment rather than a product line. The competitive question is whether Google productizes Stitch into a paid tier or folds it into Antigravity's agent toolset before [[v0]] and Figma close the multimodal gap.

## See Also

- [[v0]] — closest competitor in the design-to-code segment
- [[Lovable]] — adjacent in prompt-to-UI
- [[Magic Patterns]]
- [[Antigravity]] — Google's IDE complement
- [[Google Code Assist]]
- [[Vibe Coding Platforms]]
