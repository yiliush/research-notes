---
tags: [concept, vibe-coding, ai-coding, karpathy, terminology]
created: 2026-05-28
---

# Vibe Coding

Vibe coding is the practice of building software by describing intent in natural
language and letting an LLM produce the code, with the human accepting outputs
on feel rather than line-by-line review. The term reframed AI-assisted coding
as a mode where the artifact (the source) recedes and the outcome (the running
app) is the only thing the operator cares about.

## Origin

Andrej Karpathy coined the phrase on X on February 2, 2025:

> "There's a new kind of coding I call 'vibe coding', where you fully give in
> to the vibes, embrace exponentials, and forget that the code even exists.
> It's possible because the LLMs (e.g. Cursor Composer w Sonnet) are getting
> too good."

He described talking to Composer with SuperWhisper, accepting diffs without
reading them, and copy-pasting error messages back into the chat until the
problem went away. He framed it as appropriate for throwaway weekend projects,
not production code.

Merriam-Webster added the term to its "slang & trending" list in March 2025.
Collins English Dictionary named it Word of the Year for 2025.

## What It Means In Practice

- The operator works in natural language, not source files
- The LLM owns the code; the human owns the brief and the verdict
- Acceptance is behavioural: does the app do what I asked, in the preview?
- Errors are pasted back into the chat rather than read
- The category of tools enabling this (Bolt, Lovable, v0, Replit Agent, Cursor
  Composer) collapsed the gap between "I have an idea" and "there is a URL"
  from weeks to minutes

Simon Willison drew a useful boundary in March 2025: not all AI-assisted
programming is vibe coding. If you read every diff before you accept it, you
are pair-programming with an AI. Vibe coding specifically means giving up that
review step.

## The Critique

The category produced its first major security incident in May 2025. A
researcher scanned 1,645 apps in Lovable's own showcase and found 170 (10.3%)
with missing or broken Supabase Row Level Security policies, exposing names,
addresses, phone numbers, payment records and debt amounts from live apps. The
disclosure was tracked as CVE-2025-48757. Lovable's initial response was that
the exposure was "intentional behaviour" and pointed at its documentation. The
incident became the canonical example of the failure mode.

Other concerns crystallised through 2025-2026:

- **Maintainability.** AI generates a different idiom each session (async/await
  one day, promise chains the next). Codebases accumulate stylistic incoherence
  that compounds.
- **The "vibe coding tax."** Senior engineers describe AI output as
  "built for now, not for later" — it has no stake in what it generates. Studies
  cited through 2025-2026 reported AI-generated code roughly 1.7x more likely
  to contain major logic errors and 2.74x more prone to security vulnerabilities
  than human-written code.
- **Accountability vacuum.** When the operator never read the code, there is
  no one in the loop who can debug the production incident. The platforms
  (Lovable, Bolt) end up absorbing support burden they did not price for.
- **Andrew Ng's reframing** ("AI-assisted coding" rather than "vibe coding")
  pushed back on the term itself, arguing that responsible practitioners still
  read the diff.

## The Industry Response

By mid-2026 the category split:

- **Pure vibe** tools (Lovable, Bolt early days, Create.xyz, a0.dev) leaned
  into the non-engineer market — designers, PMs, indie hackers, agencies
- **Hybrid** tools (v0, Replit Agent, Tempo) shipped Git integration,
  diff review, VS Code-style editors, code download — quietly conceding that
  serious users want to read the code
- **Spec-driven** tools (Tessl, GitHub Spec Kit) reframed the problem: the
  artifact you maintain is the spec, not the code; the LLM regenerates code
  from spec. This is the maintainability answer to Karpathy's framing.

The term itself outgrew its origin. By 2026 "vibe coding" is the umbrella
label for the entire browser-based prompt-to-app category, regardless of how
much code review actually happens inside it.

## See Also

- [[Vibe Coding Platforms]]
- [[Bolt.new]]
- [[Lovable]]
- [[v0]]
- [[Replit Agent]]
- [[Tessl]]
