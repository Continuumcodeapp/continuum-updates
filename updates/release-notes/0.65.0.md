# Continuum 0.65.0

Windows and Linux grow up: the desktop app gets working onboarding, real chat, rich
transcripts, and a Mac-parity Code tab. Alongside it, org admins get real governance over
hosted inference, Code becomes account-wide across your devices, and a batch of Mac
reliability fixes land.

## Features

- **Windows & Linux desktop, for real.** The Electron client now onboards end to end, runs
  live chat, renders rich transcripts, and ships a Code tab at Mac parity — the cross-platform
  app is a first-class client, not a preview. (#1212)
- **Account-wide Code, across every device.** The Code sidebar spans your whole account with
  seamless enrollment and cross-device usage upload, so sessions and usage follow you between
  machines instead of living on one host. (#1215, #1216)
- **Org-admin governance for hosted inference.** Organization admins can set per-member caps
  and budgets, get spend alerts, and approve access — full control over who consumes hosted
  models and how much. (#1202)
- **Relay controllers can reach sessions.** The Mac daemon unblocks `/sessions` for relay
  controllers and auto-uploads usage every 30 minutes; web gains Create-PR parity. (#1216)

## Fixed

- **Worktree sessions are reliable.** Creating a session no longer hangs on worktree setup,
  and Local sessions can be created with no worktree at all. (#1208, #1210)
- **Chat history is there on first render.** Opening the sidebar restores your chat history
  immediately instead of showing a blank pane. (#1207)
- **Slash skills fire on the first Return** — no more swallowed first send — and
  agent-invoked skill expansions no longer render as your own chat bubbles. (#1205, #1211)
- **Symlinked skill docs open.** Markdown skill documents that are symlinks now open correctly
  on Mac. (#1203)
- **The relay survives restarts.** Relay restarts and dead links no longer strand Mac, iOS, or
  analytics — connections recover cleanly. (#1209)
- **Updater popover shows what changed** with real update summaries instead of a bare version
  bump. (#1204)
- **Primary buttons are never orange** — the primary CTA now always uses the correct accent.
  (#1206)

## Under the hood

- Cross-device usage upload and seamless device enrollment underpin the account-wide Code
  experience. (#1215)
- Integration content validated end to end after the stacked-PR land, with lost pieces
  restored. (#1217)
