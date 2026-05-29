---
tags: [vibe-coding, browser-based, prompt-to-app, lovable, supabase, ade]
created: 2026-05-28
---

# Lovable

Lovable is the Stockholm-based vibe coding platform that grew from
GPT Engineer (an open-source side project) into the fastest revenue ramp
in software history. By design it hides the code from the user entirely:
you chat, you watch the app appear in a preview, you publish. It is the
purest expression of the non-engineer thesis.

## Origin

Anton Osika built GPT Engineer as an open-source CLI tool in mid-2023 —
"describe what you want, let GPT-4 write the code." The repo hit 50K+
GitHub stars within months. In late 2023 he launched "GPT Engineer App"
as a hosted product. In December 2024 the product was renamed Lovable.

## Funding & Traction

- Pre-seed and seed: undisclosed early rounds
- Series A: $200M led by Accel, July 2025, $1.8B valuation. Participants:
  20VC, byFounders, Creandum, Hummingbird, Visionaries Club.
- Series B: $330M led by CapitalG and Menlo Ventures, December 18, 2025,
  $6.6B valuation. Participants: NVentures, Salesforce Ventures,
  Databricks Ventures, Atlassian Ventures, HubSpot Ventures.
- Total raised: $653M across four rounds.

ARR trajectory (per Sacra estimates and company statements):

| Date | ARR |
|------|-----|
| July 2025 | $100M (8 months post-launch) |
| November 2025 (Slush) | $200M |
| December 2025 | $250M |
| January 2026 | $300M |
| February 2026 | ~$400M |

CEO Anton Osika claimed at Slush 2025 that Lovable reached $100M ARR
"faster than OpenAI, Cursor, Wiz, and every other software company in
history." User count: 2.3M+ by early 2026.

## Product

You start with a single chat prompt. Lovable proposes a working app in
the preview pane within seconds. No file tree by default — the code is
viewable via a "Code" toggle but the primary interface is the chat plus
preview. You publish to a `*.lovable.app` URL with one click; custom
domains and GitHub export are paid features.

**Generated stack**: React + Vite frontend. Supabase for auth, database,
storage. Stripe for payments. Tailwind for styling. The Supabase
integration is so tight that "Lovable app" effectively means "Supabase
app."

**Models**: Multi-model with Claude as the workhorse. The "Lovable Agent"
update in 2025 introduced a planning step before code generation.

## Pricing (May 2026)

Pricing is credit-based and tiered around message/generation counts:

| Tier | Approx. price | Use |
|------|----------------|-----|
| Free | $0 | small daily credit allotment |
| Pro | $25/mo | individual builders, private projects |
| Teams | starting ~$30/user/mo | shared workspaces, pooled credits |
| Enterprise | custom | SSO, support, governance |

Exact numbers shift; the company iterates pricing roughly quarterly.

## Differentiators

- **Pure non-engineer UX.** Lovable hides the code harder than any peer.
  This is both the moat (designers and PMs adopt it on first try) and the
  liability (the May 2025 RLS incident).
- **Distribution velocity.** The growth rate is the differentiator. No
  other platform in the category onboarded users this fast.
- **Tight Supabase coupling.** Apps come with auth, DB, RLS scaffolding,
  and a real production backend out of the box. The flip side: Lovable
  inherits every Supabase failure mode, including the one that became
  CVE-2025-48757.
- **Lovable Agent** introduced an explicit planning phase, narrowing the
  gap with Tempo and Replit Agent on architecture-first generation.

## The Security Incident

In May 2025 security researcher Matt Palmer scanned 1,645 apps from
Lovable's own showcase. 170 (10.3%) had missing or broken Supabase Row
Level Security policies. Attackers could dump full user tables — names,
addresses, phone numbers, payment records, debt amounts — using the
public anon key embedded in the client. The vulnerability was tracked
as CVE-2025-48757.

Lovable's response was widely criticised as inadequate: the company first
called the exposure "intentional behaviour," then blamed its documentation
and its bug bounty partner. Reporting in April 2026 (Cyber Kendra, The
Next Web) alleged the underlying API exposure persisted for 48 days after
the bug report was closed. The episode is the canonical "vibe coding
security tax" case study. See [[Vibe Coding]].

## See Also

- [[Vibe Coding Platforms]]
- [[Vibe Coding]]
- [[Bolt.new]]
- [[v0]]
- [[Replit Agent]]
