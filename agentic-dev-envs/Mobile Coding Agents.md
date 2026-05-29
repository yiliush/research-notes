---
tags: [cluster, mobile-coding, ade-adjacent, surface-category]
created: 2026-05-28
---

# Mobile Coding Agents

Mobile coding agents are the 2025–2026 surface category: the phone as a remote control for an agent doing real work elsewhere. Within roughly six months — October 2025 (Claude Code in Claude iOS) to May 2026 (Codex Mobile in ChatGPT) — every major coding-agent vendor shipped a mobile surface. The architecture is consistent: phone is a thin client, execution happens on a paired desktop session or in the cloud. The exception is Replit, whose mobile app drives its own cloud runtime end-to-end.

## Why It Belongs In This Vault

The mobile-agent surface only makes sense once agents run long enough that users want to leave the laptop. Cursor 2.0's Background Agents, Codex Cloud, Claude Code's long-running tool loops, and GitHub's cloud coding agent all extend task duration past the point where staring at a screen makes sense. The phone is the obvious supervision surface: kick off a task on the laptop, approve and steer from the phone while doing something else. This is a different mental model from a "mobile IDE" — none of these products are trying to be that.

## The Architectures

**Phone-as-remote.** [[Cursor Mobile]], [[Codex Mobile]], and [[Claude Code Mobile]] all run agents on a paired Mac (Codex), a devbox (Cursor), or any machine running the CLI (Claude Code). The phone sends prompts, sees diffs, approves commands, gets push notifications. Files and credentials never leave the desktop. Apple's app-sandboxing rules effectively force this architecture.

**Phone-as-thin-client-to-cloud.** [[GitHub Mobile Copilot]] runs the coding agent in GitHub's cloud. No paired desktop needed — the phone is a fully self-contained client to a cloud agent. This is the only architecture where the phone is materially useful without a laptop.

**Phone-as-runtime-frontend.** [[Replit Mobile]] runs everything on Replit's cloud — build, deploy, host. The mobile app is a full creator surface; the same agent loop that runs on the web works on the phone. Replit's May 2026 Apple-policy thaw made this fully shippable.

## The Distribution Picture

- [[Codex Mobile]] reaches 4M+ weekly Codex users via ChatGPT — the largest install footprint by default.
- [[GitHub Mobile Copilot]] reaches tens of millions of devs already on GitHub Mobile — largest by latent reach.
- [[Claude Code Mobile]] is the only iOS-and-Android-and-Xcode story — Apple partnership matters.
- [[Cursor Mobile]] is iOS-only as of April 2026; Android is PWA-only.
- [[Replit Mobile]] is the only end-to-end mobile creator loop — phone in, deployed app out.

## What Mobile Is Bad At

You cannot meaningfully write or edit code on a phone. None of these products pretend otherwise. What the phone does well: approving commands, reviewing diffs, steering an active task, kicking off long-running work, monitoring multiple parallel agents. The mobile surface is supervision, not authorship.

## Entities

- [[Cursor Mobile]] — iOS remote for Cursor agents; model picker; Background Agents focus
- [[Codex Mobile]] — ChatGPT-app surface; iOS and Android; free-tier inclusive
- [[Claude Code Mobile]] — iOS + Android + Xcode integration; Remote Control
- [[GitHub Mobile Copilot]] — cloud-agent thin client; no Mac dependency
- [[Replit Mobile]] — end-to-end mobile creator runtime

## See Also
- [[Claude Code]]
- [[Cursor]]
- [[Replit]]
- [[GitHub Copilot]]
- [[Codex CLI]]
- [[Codex Cloud]]
