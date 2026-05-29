---
tags: [tool, mobile-coding, replit, ade-adjacent, vibe-coding]
created: 2026-05-28
---

# Replit Mobile

Replit Mobile is the standalone iOS/Android Replit app that, by mid-2026, became the most fully realized "build an app from your phone" surface in the cluster. Replit was the first company to put a real software-creation agent into a mobile app (the "Software Creation Agent on iOS and Android" launch), and by May 2026 Agent 4 on mobile supports parallel agents, team collaboration via merge flows, and project viewing across workspaces — distinct from the Cursor/Codex/Claude pattern of "phone as remote for desktop session."

## Origin
- Replit founded 2016 by Amjad Masad, Faris Masad, Haya Odeh. Headquartered in San Francisco.
- Long-standing mobile presence — Replit's iOS and Android apps predate the agent era as IDEs for the browser-based runtime.
- 2024–2025: Replit Agent expanded mobile capability significantly; agent could build deployable apps directly from the phone.
- May 2026: Masad publicly announced Replit had "worked things out with Apple" and shipped Replit Agent 4 to mobile users with parallel agents, merge flows, and cross-workspace project viewing.

## Adoption
- Replit's overall ARR crossed $100M+ during 2025; mobile is positioned as a non-laptop creator funnel rather than a separately monetized SKU.
- The "Vibe Code Anywhere" framing is explicit in app store listings.
- Strong attach among indie hackers, students, and emerging-market developers without a laptop-first setup.
- The May 2026 Apple negotiation matters: Apple's app review historically treated code-generating-and-running apps as edge cases, and Replit reportedly worked through enough policy that Agent 4 ships full functionality on iOS.

## Product
- Native iOS and Android apps wired into Replit's cloud runtime (build, deploy, hosting, ReplitDB, storage).
- Replit Agent 4 on mobile — prompt-to-app with parallel agents running on a single project.
- React Native + Expo support — generate iOS/Android apps from a phone, preview via Expo QR on-device, walk through App Store submission.
- Merge flows for team collaboration — review and accept agent outputs across collaborators.
- View and manage multiple projects/workspaces from a single mobile session.

## Pricing
- Free tier — limited compute and agent credits.
- Replit Core — ~$25/month, full agent access.
- Teams and Enterprise tiers — custom; same mobile access included.

## Differentiators
- Mobile is a real runtime, not a remote — Replit can execute, deploy, and host the app on the same backend whether the developer is on a laptop or a phone. Cursor, Codex, and Claude Code all require a paired desktop.
- The only company shipping a "phone makes a deployed app" loop end-to-end as a first-class product.
- Tight coupling between Agent 4 and the runtime is exactly the vertical-integration thesis from Replit's overall positioning — mobile is the surface where that integration matters most.
- Limits: anything outside React Native / Expo / web is hard to do from the phone; the App Store policy environment remains a risk vector even after the May 2026 thaw.

## See Also
- [[Mobile Coding Agents]]
- [[Replit]]
- [[Replit Agent]]
- [[Cursor Mobile]]
- [[Vibe Coding]]
