---
tags: [tool, voice-coding, dictation, open-source, ade-adjacent]
created: 2026-05-28
---

# Whispering

Whispering is the OSS, local-first dictation app that occupies the "I don't want my voice going to a startup's cloud" slot in this cluster. MIT-licensed, cross-platform, and built to chain local Whisper/Parakeet inference with optional cloud providers (Groq, OpenAI, ElevenLabs) when the user opts in.

## Origin
- Open-source project; primary maintainer Braden Wong (the Show HN landed on Hacker News in 2025).
- Native desktop apps (Tauri/Svelte) for macOS, Windows, Linux, plus a browser version for quick trials.
- MIT license; community contributors.
- Adjacent project OpenWhispr covers similar ground (local Whisper + Parakeet, BYOK) — both reflect a broader OSS reaction to Aqua/Wispr's cloud-default posture.

## Adoption
- The default recommendation in privacy-conscious developer threads; the "actually works" answer when Linux users ask for a dictation tool.
- No public revenue or user numbers — it's free software. Star/fork counts on the GitHub repo are the main signal.

## Product
- Hotkey-driven dictation: press, speak, transcribe, transform, paste at the cursor.
- Pluggable transcription backends:
  - Local: whisper.cpp, Speaches, faster-whisper, NVIDIA Parakeet.
  - Cloud (BYOK): Groq, OpenAI, ElevenLabs, Deepgram.
- Custom transforms — chain LLM passes after transcription (clean up, format as code, translate).
- Local-first by default — audio doesn't leave the machine unless the user picks a cloud backend.

## Pricing
- Free, open source.
- If using cloud backends: pay-as-you-go to the provider directly (typically $0–5/month at normal usage).

## Differentiators
- Truly local-first — the audio path goes machine to local model and nowhere else by default. Aqua and Wispr are cloud-default.
- Bring-your-own-model — swap in whatever STT you like; not locked to a vendor's proprietary model.
- Linux support that actually works — a low bar most competitors don't clear.
- No moat against Aqua-style accuracy for code — local Whisper variants still mangle code tokens compared to Avalon-class trained-on-code models. Whispering's bet is privacy and openness, not best-in-class accuracy.

## See Also
- [[Voice Coding]]
- [[Aqua Voice]]
- [[Wispr Flow]]
- [[Talon Voice]]
