---
tags: [company, ai-ide, google, antigravity, ade-cluster, agent-native]
created: 2026-05-28
---

# Antigravity

Antigravity is Google's agent-first development platform, launched November 18, 2025 alongside Gemini 3. It is the IDE that absorbed the [[Windsurf]] founding team after Google's $2.4B reverse-acquihire in July 2025, and it represents Google's bet that the editor-with-AI paradigm (Cursor, Copilot) is being superseded by a fleet-management paradigm where developers orchestrate multiple autonomous agents rather than pair-program with one.

## Origin

- July 11, 2025: Google paid $2.4B in a non-exclusive licensing + reverse-acquihire deal that brought Windsurf CEO Varun Mohan, co-founder Douglas Chen, and roughly 40 senior Windsurf engineers into Google DeepMind. The deal followed the collapse of OpenAI's $3B Windsurf acquisition.
- November 18, 2025: Public preview launch alongside Gemini 3. Available on macOS, Windows, Linux. Free for individuals.
- Developers immediately recognized the editor as a heavily modified VS Code fork sharing UX DNA with Windsurf — the Windsurf team built Google's IDE inside four months.

## Product

- **Two-pane architecture**: Editor view (VS Code-style code surface) and Agent Manager view (mission control for parallel agents). The split mirrors the IC/manager distinction.
- **Agent Manager**: spawn, monitor, and approve up to 5 parallel agents running across separate sandboxes. Each shows status, artifacts, and pending human-approval requests.
- **Artifacts**: explicit deliverables (plans, diffs, screenshots, browser recordings) that the agent produces alongside the code change. Google frames these as the solution to the "trust gap" — instead of claiming "I fixed it," the agent must produce evidence the developer can scan.
- **Browser-native execution**: agents drive a real browser as a tool, taking screenshots and recordings as part of every web-related task.
- **Model selection**: native support for Gemini 3 Pro and Gemini 3 Flash, plus Claude Sonnet 4.6, Claude Opus 4.6, and GPT-OSS-120B. Multi-vendor by default — unusual for a hyperscaler IDE.

## Strategic Position

- Antigravity is Google's consolidation play across its developer-AI surface. Google announced that Gemini Code Assist IDE extensions and Gemini CLI for individual / AI Pro / AI Ultra tiers stop serving requests on June 18, 2026 — users are migrated to Antigravity. See [[Google Code Assist]].
- The bet: the IDE category is shifting from "AI in your editor" to "you manage agents that do the work." Antigravity is staffed by the team that already built one category-defining product ([[Windsurf]]) and now has Gemini 3, browser tools, and Google's compute behind it.
- Free-for-individuals pricing is the wedge against [[Cursor]]'s $20–$200/month tiers. Google is paying for adoption while it owns both the model and the runtime.
- The acquihire structure was widely criticized as an antitrust workaround — Google got the team and the tech without buying the company, leaving Windsurf-the-shell to be picked up by Cognition. See [[The Windsurf Saga]].

## See Also

- [[Windsurf]] — the product Antigravity is descended from
- [[The Windsurf Saga]] — the OpenAI/Google/Cognition carve-up
- [[Cursor]] — the entrant Antigravity is positioned against
- [[Google Code Assist]] — being deprecated into Antigravity
- [[Gemini CLI]]
- [[AI-Native IDEs]]
- [[Market Landscape]]
