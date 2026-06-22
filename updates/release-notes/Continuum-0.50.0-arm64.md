# Continuum 0.50.0

A big chat-and-transcript release: full session history, categorized action groups that collapse to a clean summary at the end of a turn, Codex diffs with clickable file links, tinted message bubbles, reliable cross-provider model switching, and a wide sweep of iOS Usage and Settings improvements.

## New & improved

- **Full chat history in the Code/Sessions tab.** Opening a session now loads its entire transcript instead of just the tail — scroll up all the way to the first turn. (#652)
- **Categorized action groups + tidy end-of-turn collapse.** While a turn runs, tool calls group into labeled rows (commands, reads, writes, search, …); once the turn finishes it collapses to a one-line summary you can expand on demand. (#640, #637)
- **Codex diffs & clickable file links.** Codex `apply_patch` edits render as colored diffs, and `file:line` references in the transcript resolve to real, clickable links that open the file. (#646)
- **Cross-provider model switching actually switches.** Toggling a running session to another provider's model (e.g. Codex → Claude Opus) now respawns on the new model instead of silently no-op'ing. (#645)
- **Warm tint for your messages.** Customer message bubbles get a subtle terra-cotta wash so your turns stand apart from the assistant's, on Mac and iOS. (#649)
- **Both Claude accounts stay current.** A tied second Claude account's usage gauge is no longer starved by the primary's polling. (#638)
- **Plan / Code pill toggles reliably.** Clicking the permission pill flips and persists the mode (and never silently grants full bypass on a later model/effort change). (#644)
- **Live active-session indicator.** The data-stream "cable" on the focused worktree lights from a model-owned signal, so it tracks real streaming state. (#643)
- **iOS catches up to your Mac.** Model trays (chat + new session) show exactly the vendors you've enabled on the Mac; the Usage tab now surfaces every enabled provider plus dedicated OpenCode and Grok strips. (#647, #651)
- **Anonymous usage sharing (optional).** Continuum can report aggregate token and cost totals — no prompts, file paths, repo names, or account details — to help improve it. On by default, with a one-tap opt-out in **Settings → Your Preferences**. (#650)
- **Settings & polish.** Settings buttons and segmented controls align to the design system, Save Costs moves under Workspaces, queued follow-up actions read as clickable, and notifications are branded "Continuum." (#648, #641, #639, #642)

Ships build 263 for Mac (signed Sparkle feed).
