# Continuum 0.57.13

The web dashboard becomes a full peer of the Mac app — you can now run Code, Chat, Usage, and Settings in the browser against a connected host — plus Sonnet 5 and Fable 5 in the model picker and a couple of Mac fixes.

## New

- **The web dashboard is now a 1:1 peer of the Mac app.** Code, Chat, Usage, and Settings all work from the browser, driving a connected host (your Mac or a Linux agent) over the same end-to-end encrypted relay the apps use — a live `#/code` workbench (sessions, transcript, diff/PR, terminal, model picker, host skills), `#/chat` (solo + multi-model broadcast), `#/usage` (live gauges + spend history), and `#/settings` (devices, workspaces, providers, diagnostics). A heterogeneous fleet is gated by what each host actually serves, so the browser only offers what the connected host supports. (#826)
- **Sonnet 5 and Fable 5 in the model picker.** Both new Claude models are now selectable across the model pickers. (#825)

## Fixed

- **Generated workspace display names are correct.** Auto-generated workspace names no longer render with the wrong label. (#823)
- **No more empty release-notes panel in the updater.** When Continuum is already up to date, the updater popover no longer shows a blank "what's new" panel. (#822)

Ships build 284 for Mac (signed Sparkle feed).
