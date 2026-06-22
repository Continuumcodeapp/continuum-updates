# Continuum 0.45.0

A workspace-polish release: App Shots get a global keyboard trigger, Claude can run on a new SDK runtime, the composer takes drag-and-drop, and assistant replies finally render as real Markdown — on top of a long list of Code-sidebar and chat fixes.

## New & improved

- **App Shots, reworked.** Capture the window of whatever app you're in by pressing both ⌥ Option keys — Continuum teleports forward and drops the shot into your prompt — with a guided Screen Recording permission wizard the first time you turn it on. (#546, #547)
- **Selectable Claude SDK runtime.** Claude sessions can now run on a new SDK/ACP runtime alongside the classic CLI, switchable from Settings. (#565)
- **Drag-and-drop attachments.** Drop files straight onto the composer to attach them to your prompt. (#554)
- **Land PRs from the sidebar.** A new repo-level "Land PRs" action spins up an agent to review and land your open pull requests. (#562)
- **Rename anything.** Right-click to rename spawn groups in the Code sidebar (#569), and rename any account tag — including "Default" — from a hover-pencil in Settings (#570).
- **Markdown-formatted replies.** Assistant answers now render as structured Markdown — headings, lists, quotes, and code blocks — instead of flat text, on both Mac and iOS. (#567)
- **Archive keeps you in flow.** Archiving the session you're in advances to the next live session in the same repo instead of dropping you to an empty composer. (#561)
- **Lower energy use.** The Code tab pauses its live animations and streams while it's in the background. (#560)

## Fixes

- **No more blank-until-scroll chat.** Opening a session seeds the transcript immediately instead of showing an empty pane until you scroll. (#566)
- **Steadier turn display.** The active turn stays expanded while it streams and collapses to "Thought for…" only once it's done. (#552)
- **Cleaner Code sidebar.** Session summaries are centered with the redundant branch subtitle dropped, summaries survive the first prompt, and active branch streams reattach reliably. (#551, #553, #555)
- **Diff badges hold steady.** Sidebar diff counts persist through transient git probe failures instead of blinking out. (#558)
- **Correct usage account.** Claude usage now syncs the right account's token before polling. (#563)
- **Composer polish.** De-duplicated the end-of-turn copy button, kept the attachment hover bubble inside the chat edge, tightened activity spacing, fixed shortcut-override chord recording, and made the stop button more legible. (#564, #556, #548, #549, #550)
- **Titlebar shows your PR.** A created pull request now appears in the Code titlebar, and worktree branch naming is more reliable. (#559, #557)

Ships build 257 for Mac (signed Sparkle feed). The iOS app ships the same chat-formatting and workspace improvements via TestFlight.
