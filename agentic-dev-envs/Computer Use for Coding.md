---
tags: [concept, frontier]
created: 2026-05-28
---

# Computer Use for Coding

The pattern where a coding agent operates the developer's full computer — moving the mouse, taking screenshots, clicking buttons in a real browser or IDE — rather than only writing files and running shell commands. Anthropic shipped Computer Use as a Claude capability in October 2024; the ADE category has been quietly absorbing it ever since. Most coding tasks don't need it. The ones that do are precisely the ones the rest of the harness can't handle.

## When It Matters

- **Live debugging of a running app** — agent takes a screenshot of the browser, sees the broken state, fixes the code, refreshes.
- **Visual regression testing** — agent compares rendered output against design specs.
- **GUI-driven workflows the codebase can't expose** — admin panels, cloud consoles, third-party SaaS dashboards where the agent has to click through to reproduce a bug.
- **Design-to-code review** — agent compares the Figma against the live preview.
- **Form filling and end-to-end test authoring** — the actual click-around is the spec.

## Who Ships It

- **[[Claude Code]]** — Computer Use available via the broader Claude platform; agents can request screenshots and mouse/keyboard control.
- **[[OpenHands]]** — full browser-use plus screenshot loop natively built into the agent harness.
- **[[Devin]]** — has its own integrated browser the agent operates as part of every task.
- **[[Cursor]]** and **[[Windsurf]]** — limited integrated browser preview; not full computer use.
- **[[Bolt.new]]** and **[[Lovable]]** — agent sees its own preview; closest thing to computer-use in vibe coding.
- **Browser Use library, Skyvern, Anchor Browser** — standalone agent-browser libraries that any harness can adopt.

## Why Most Coding Doesn't Need It

The unified diff + shell loop covers ~90% of coding tasks. Computer Use is expensive (screenshots are large in tokens), slow (each click is a tool call), and error-prone (UIs change). For pure code editing, it's strictly worse than reading files and writing patches.

## Why the Other 10% Matters

The 10% includes:
- Bugs that only reproduce in the browser (CSS, layout, animation).
- Integrations with third-party services that have no programmatic API.
- Visual confirmation that an agent's "done" state is actually done.
- E2E test authoring, which is inherently a click-around-and-record task.

Vendors who serve this 10% (Devin, OpenHands, the design-to-code cluster) charge more per task and own higher-trust workflows.

## The Latency Problem

Computer Use multiplies the latency of every step:
- A file edit takes ~1 second.
- A click + screenshot round-trip can take 5–15 seconds.
- A "navigate to admin panel, change a setting, verify" sequence takes minutes.

This is why Computer Use is overwhelmingly a [[Background Agents|background-agent]] feature, not an inner-loop one.

## See Also
- [[Background Agents]]
- [[Long-Horizon Coding]]
- [[Devin]]
- [[OpenHands]]
- [[Design-to-Code Agents]]
