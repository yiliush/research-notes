---
tags: [cluster, design-to-code, vibe-coding, ade-adjacent, surface-category]
created: 2026-05-28
---

# Design-to-Code Agents

Design-to-code is the wing of vibe coding where the source of truth is a UI — a Figma file, an uploaded screenshot, a natural-language prompt that produces interconnected screens — and the output is production-ready code in React, Vue, Angular, Svelte, Flutter, Kotlin, or SwiftUI. The category has been around since 2017 (Anima's pixel-perfect HTML exporter), but the AI-era turn — Galileo's text-to-UI in 2023, Visual Copilot in late 2023, Stitch in 2025 — collapsed the design-to-handoff problem into something a non-engineer can drive.

## Why It Belongs In This Vault

Design-to-code is where the prompt-to-app stack and the traditional front-end developer workflow intersect. [[Bolt.new]], [[Lovable]], and [[v0]] start from "describe an app, get a deployed URL." Design-to-code tools start from "describe a UI or import a design, get code your engineers will accept." The difference is the integration story: design-to-code tools are upstream of the developer, not a replacement for the developer. Builder.io's explicit "Figma to Cursor to codebase" pitch is the clearest articulation.

## The Three Lineages

**Figma-plugin first.** [[Locofy]], [[Anima]], and [[Builder.io]] (Visual Copilot) live as Figma plugins. The designer works in Figma; the plugin extracts a clean code representation; the developer gets framework-specific output. This is the workflow with the most enterprise traction — agencies, in-house product teams, design systems.

**Text-to-UI first.** [[Galileo AI]] originated this, [[Stitch]] now embodies it. Type a prompt, get a canvas with screens. No Figma required. This is the wing more aligned with [[Vibe Coding]] — design is generated, not imported.

**Hybrid.** [[Anima]]'s AI Playground is also a prompt-to-app surface with built-in databases. [[Stitch]] exports to Figma. Builder.io's Fusion connects designs through AI IDEs into the codebase. The pure-plugin and pure-text-to-UI poles are blurring.

## Who Survives

- [[Galileo AI]] — acquired by Google May 2025, became Stitch. The acqui-hire route.
- [[Stitch]] — free in Google Labs; aggressive feature pace through 2026; DESIGN.md spec format open-sourced.
- [[Locofy]] — Large Design Models brand; broadest framework matrix including Flutter; token-based pricing.
- [[Builder.io]] — Mitosis compiler + AI model + LLM pass; cleanest technical pipeline; explicit AI-IDE handoff.
- [[Anima]] — IBM-backed; MCP server for Cursor and Claude Code; Frontier component-mapping; broadest scope.

## The DESIGN.md Moment

Google's April 2026 open-sourcing of DESIGN.md under Apache-2.0 is the first cross-vendor design-system spec format. Claude Code, Cursor, and GitHub Copilot can read it; teams can export from Stitch and import elsewhere. The signal: design systems are becoming a first-class context format for coding agents, the same way `.cursorrules` and `CLAUDE.md` did for project conventions.

## What's Hard

The persistent failure mode across the entire category: generated code that doesn't match the project's existing components. AI generates a fresh button; the codebase already has eight button variants in a design system; the output looks foreign and gets rewritten by hand. [[Anima]]'s Frontier VS Code extension addresses this directly; [[Builder.io]]'s Fusion attacks the same problem via AI-IDE integration. Whoever wins this category solves the component-mapping problem first.

## Entities

- [[Galileo AI]] — pre-acquisition text-to-UI pioneer, acqui-hired by Google
- [[Stitch]] — Google Labs design-to-code agent; streaming + voice + multi-screen + DESIGN.md
- [[Locofy]] — Figma/Penpot, multi-framework including Flutter, LDM-branded
- [[Builder.io]] — Visual Copilot, Mitosis, AI-IDE handoff focus
- [[Anima]] — AI Playground + Figma + Frontier + MCP server

## See Also
- [[Vibe Coding]]
- [[v0]]
- [[Bolt.new]]
- [[Lovable]]
- [[Magic Patterns]]
- [[Model Context Protocol (MCP)]]
