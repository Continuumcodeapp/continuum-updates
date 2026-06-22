# Continuum 0.54.0

A Code-workbench polish release: sub-agents get their own transcript row, attachment cards show per-file diff stats, and a batch of chat/composer fixes — plus the multi-provider chat-surface unification wraps up.

## New & improved

- **Sub-agents render as their own transcript row.** Spawned sub-agents (Claude `Task` / `spawn_agent`) now appear as a dedicated Agent row — agent glyph, spawn description, and a live elapsed timer — instead of being buried inside the grouped "Ran N commands" disclosure. (#697)
- **Diff stats on composer attachment cards.** Each tracked file you attach now shows its working-tree diff as `+N` (green) / `−M` (red), so you can see at a glance how much a file changed before you send. (#698)
- **Repo "+" honors your defaults.** The Code sidebar's repo **+** quick-spawn now uses your Settings → Your Preferences provider, model, effort, and Plan/Code mode instead of a hardcoded Codex/Plan default. (#690)

## Fixed

- **Instant stream + timer on send.** The chat footer's data-stream animation and "time active" readout now start the moment you hit send, in lockstep with the sidebar, instead of lagging a render behind. (#691)
- **Stable, smooth Mac transcript scrolling.** Both Mac chat transcripts now render eagerly, so the scrollbar stops jumping and resizing as you scroll — and the whole conversation renders, not just the tail. (#692)
- **Attachments with spaces in the path open correctly.** Clicking a composer attachment whose path contains a space (like "Application Support") now opens the real file instead of a dead "file no longer exists" tab. (#693)
- **Turn-rail hover preview stays on-window.** The Code-tab turn-rail hover preview no longer clips off the right edge of the window, and now shows the prose of the turn instead of the raw `@path`. (#694)
- **Calmer command palette.** The ⌘K and slash (`/`) command palettes use a neutral selection highlight — the brand accent is reserved for the sessions sidebar and your own messages — and skill-source tags are now greyscale. (#695)
- **Stuck-turn watchdog + consistent Code mode.** Code sessions reliably run with approvals bypassed across every provider, a watchdog recovers stuck turns, and tab branch subtitles stay consistent. (#696)

## Under the hood

- Completed the multi-provider chat-surface unification: the normalized event store and shared materializer are now always-on, and the strangler-fig feature flags have been retired. (#699, #700, #701, #702)

Ships build 268 for Mac (signed Sparkle feed).
