---
tags: [tool, voice-coding, dictation, ade-adjacent, yc, startup]
created: 2026-05-28
---

# Aqua Voice

Aqua Voice is the system-wide AI dictation app that became the de facto voice input layer for a meaningful slice of Claude Code and Codex power users in 2025–2026. It started as a "voice-driven document editor" out of Y Combinator W24 and pivoted into the "input layer for the AI agent era" once it became clear that the bottleneck on agentic coding was no longer the model — it was the speed of getting English into the prompt box.

## Origin
- Founded 2023 by Finn Brown (CEO) and Jack McIntire (CTO). San Francisco.
- Brown is dyslexic; the founding origin is his frustration with Dragon Professional and the lack of a modern equivalent.
- Y Combinator W24.
- Pre-seed ~$500K led by Y Combinator and Pioneer Fund. ARR ~$330K as of September 2025 (per public profiles).
- Avalon, Aqua's proprietary speech-to-text model, shipped August 2025, replacing the prior Whisper-based pipeline.

## Adoption
- More than 50% of the user base is in Japan — driven organically by programmers escaping the friction of Japanese keyboard input when working with AI coding agents. This is one of the most surprising distribution patterns in the cluster.
- Heavy reported usage among Claude Code and Cursor users who prefer talking to the agent rather than typing the prompt — the workflow Karpathy described when coining "vibe coding" (SuperWhisper at the time, Aqua now).
- Distributed via direct download for macOS and Windows; no mobile.

## Product
- System-wide dictation — hotkey, speak, text appears wherever the cursor is.
- Avalon model trained specifically on prompt-style speech, code, and email (deliberately not audiobooks or meetings).
- Claimed accuracy: 97.4% on coding/AI terms vs Whisper Large V3's 65.1%; 3.2% WER on LibriSpeech-clean (Google Docs Voice Typing ~5.5%).
- Custom dictionary, app-specific formatting, AI editing (auto-punctuation, filler-word removal, rewriting in place).
- Latency tuned for prompt-style use: short utterances finalize fast rather than waiting for sentence boundaries.

## Pricing
- Free tier with limited monthly minutes.
- Pro: $8/month for individuals.
- Business and Enterprise tiers exist with team management and custom retention.

## Differentiators
- Code-trained STT — every other system-wide dictation app inherits Whisper's audiobook bias and mangles `kebab-case`, `snake_case`, and CLI flags. Avalon was explicitly trained against this failure mode.
- Prompt-shaped, not meeting-shaped — designed for short bursts at a chat box, not 30-minute transcripts.
- The Japanese power-user base is a real moat: it's nearly impossible to type Japanese fluently while context-switching into English code, and Aqua handles the mixed-language case better than alternatives.

## See Also
- [[Voice Coding]]
- [[Wispr Flow]]
- [[Talon Voice]]
- [[Whispering]]
- [[Vibe Coding]]
- [[Claude Code]]
