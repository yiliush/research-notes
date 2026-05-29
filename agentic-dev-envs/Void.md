---
tags: [tool, open-source, ai-ide, cursor-alternative, yc-backed, ade-cluster]
created: 2026-05-28
---

# Void

Void is the highest-starred open-source Cursor alternative — a VS Code fork that ships AI features (Tab, Cmd-K, agent mode) with zero backend of its own, sending all model requests straight from the editor to whichever provider the user picks. Built by the Pareles brothers (Andrew and Matthew), backed by Y Combinator. By May 2026 it has ~28.8k stars but the team has formally paused active development to explore "novel coding ideas" rather than chase feature parity with [[Cursor]] and [[Windsurf]].

## Origin
- Founded 2024 by Andrew Pareles and Matthew Pareles. SF-based. 2-person team.
- Y Combinator backed (batch not formally confirmed in public materials but widely reported as W25-adjacent — the user's premise of W25 is plausible but unverified).
- Open-sourced from day one — explicit "we are the not-evil Cursor" positioning.
- Public beta release June 2025.

## Adoption
- GitHub stars verified May 2026: ~28.8k on `voideditor/void`. Forks: 2.5k.
- Among the most-starred OSS AI IDEs in existence, alongside the Continue+derivatives cluster.
- Active Discord community despite the dev pause.
- 2,771 commits total.

## Architecture
- VS Code fork (95.3% TypeScript).
- No backend — direct client-to-provider connections. This is the privacy story.
- Model layer: bring-your-own-key for Anthropic, OpenAI, Gemini, Groq, Mistral, plus full Ollama and LM Studio support for local models.
- Features at pause: Tab autocomplete, Cmd-K inline edit, chat, agent mode with codebase reads/writes, checkpoint/diff visualization.
- License: Apache 2.0 (Void layer) + the inherited VS Code License (Microsoft's MIT-equivalent for the editor base).

## Pricing
- Free. No hosted tier. No paid product.

## Differentiators
- "No backend" is the load-bearing claim — your code never touches Void's servers. Compare to [[Cursor]] which routes through Anysphere infrastructure.
- Local-model support is genuinely first-class, not vestigial — Ollama integration works out of the box.
- 28k stars on a 2-person team is exceptional and demonstrates real demand for an OSS Cursor.
- The "pause to focus on innovation over parity" announcement (early 2026) is unusual — most YC startups would force-feature-parity through burnout.

## Strategic Position
- Dev pause is the central question. Three possible reads:
  1. Founders are pivoting to a different product (most common YC pattern).
  2. They are genuinely incubating something new and will relaunch with novel UX.
  3. They are quietly exploring an acquisition.
- Repo remains public and functional — Void is not dead, it's frozen at a working state.
- A live community fork is plausible if the pause extends, similar to how [[Aide]] inspired forks after its archive.
- The Void → Cursor delta is now mostly Composer (Cursor's in-house model) and Background Agents — both server-side features Void can't replicate without a backend, which is the whole point of Void.

## See Also
- [[Cursor]] — the target
- [[Aide]] — the other open-source VS Code fork with an AI layer
- [[Pear AI]] — the controversial alternative
- [[Continue]] — the dominant VS Code OSS extension (not a fork)
- [[AI-Native IDEs]]
- [[Green Shoots]]
