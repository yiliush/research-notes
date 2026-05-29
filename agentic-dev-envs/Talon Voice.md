---
tags: [tool, voice-coding, accessibility, oss-ish, ade-adjacent]
created: 2026-05-28
---

# Talon Voice

Talon is the OG voice-coding system — the one programmers with RSI, spinal muscular atrophy, or other hand-mobility constraints have used to write code, run shells, and control desktops since before the LLM era made voice input a productivity meme. It is not built around dictating English to an LLM; it is built around scripting your computer with grammar files that turn utterances into precise keystrokes, snippets, and commands. The community that grew around it is one of the densest engineering subcultures in accessibility tech.

## Origin
- Created by Ryan Hileman, who left a full-time engineering job to build it as accessibility software. Funded by users via Patreon and donations.
- Written in Rust (modern Talon); cross-platform (macOS, Windows, Linux).
- First public releases circa 2017; massive growth in the community grammar repos (notably knausj_talon, then talon-community) through 2020–2024.

## Adoption
- The reference tool for hands-free coding in accessibility communities. Public stories from Emily Shea, Josh Comeau, Blake Watson, and Trillium Smith document programmers who write production code entirely by voice and noise.
- 2025 conference presence at Virtual Coffee's online conference and DevOpsDays LA brought broader developer awareness.
- Not a venture-backed product. No headline funding round, no enterprise sales motion. The community grammars (knausj, community.talon, cursorless) are the distribution.
- Cursorless — a Talon-based grammar by Pokey Rule for structural code editing by voice — became the most-cited voice-coding workflow among programmers regardless of disability status.

## Product
- Three input modalities, composable:
  - Speech recognition (Conformer-based local models; previously wav2letter).
  - Noise recognition — pops, hisses, clicks as inputs.
  - Eye tracking (Tobii integration) for cursor and focus control.
- Grammar-based scripting (Python). Users write `.talon` files that map utterances to actions: keystrokes, snippets, app switching, custom Python.
- Cursorless extension layer adds tree-sitter-aware structural commands — "take this funk", "chuck arg air", "bring state past blue" — that operate on AST nodes, not characters. The result is voice-coding faster than typing for some long-time users.
- Local-first inference, no cloud dependency.

## Pricing
- Free tier (Talon Public) — full functionality, slower model.
- Talon Pro — ~$15/month via Patreon, unlocks the faster Conformer model.
- No team or enterprise tier. Funding model is donation-based.

## Differentiators
- Grammar over dictation — Talon is the only mainstream voice tool that treats programming as a structured action problem rather than a transcription problem. You don't dictate `for i in range(10):`; you say a 3-syllable command that emits the snippet.
- Cursorless — structural editing by voice is something neither Aqua, Wispr, nor Whispering can do, and it is what makes Talon faster than typing for committed users.
- Accessibility-first lineage — the user community includes people for whom this is not a productivity tool but the only way to use a computer at all. That sets the project's design priorities.
- The bus-factor risk — Hileman is a single maintainer; the dependency stack is non-trivial. Community grammars are sprawling and not always well-documented for newcomers, which gates adoption.

## See Also
- [[Voice Coding]]
- [[Aqua Voice]]
- [[Wispr Flow]]
- [[Whispering]]
