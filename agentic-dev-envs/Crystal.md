# Crystal

The first Electron-based desktop GUI for parallel [[Claude Code]] sessions. Crystal proved the desktop-app pattern that [[Conductor]] later commercialized natively. As of February 2026 the original project is deprecated and its maintainers (Stravu) have moved development to a successor product, Nimbalyst — making Crystal one of the first casualties in this cluster.

## Origin

* Repo: `stravu/crystal`.

* Built by **Stravu**, a small team building AI-collaboration tooling.

* Initially released 2025 as a parallel-Claude-Code session manager.

* License: **MIT**.

* Primary language: TypeScript (~97%) — Electron app.

## Architecture

* Electron desktop application (macOS, Linux, Windows).

* Each session runs in its own **git worktree** with its own branch.

* Underlying agents: Claude Code and Codex spawned as subprocesses.

* Built-in git operations: rebase, squash, diff view, change tracking.

* Session persistence: conversations can be resumed; sessions survive app restarts.

* Desktop notifications when an agent stalls waiting for input.

## Distribution & Adoption

* Distribution: Electron build, packaged as a Flatpak (`com.stravu.crystal`) and direct downloads.

* GitHub stars: **~3.1K** as of the project's deprecation in early 2026.

* 672 commits, 196 forks, latest release `v0.3.5` on **Feb 26, 2026**.

* README now explicitly recommends migrating to Nimbalyst.

## Pricing

* Free, OSS. Nimbalyst (the successor) appears to be moving toward a commercial product around an "AI-native workspace" rather than pure parallel orchestration.

## Current State (May 2026)

* **Deprecated.** Stravu is actively building Nimbalyst (`Nimbalyst/nimbalyst`), positioned as a broader "AI-native workspace for human + AI collaboration" — multi-editor (code, markdown, spreadsheets, diagrams) with the parallel-worktree story as one feature rather than the headline.

* Crystal still works and the repo remains available, but does not receive updates.

## Differentiators (Historical)

* First widely-adopted desktop GUI in the cluster — predates Conductor's commercial polish.

* TypeScript/Electron approach made it cross-platform out of the box (Conductor is Mac-only).

* Heavier git integration (built-in rebase/squash) than the terminal-based competitors.

## See Also

* [[Parallel Agent Orchestrators]] — cluster index

* [[Conductor]] — the native-Mac commercial successor in spirit

* [[Claude Squad]] — terminal counterpart

* [[Claude Code]]

⠀