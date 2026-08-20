# Continuum 0.96.5

## Features
- A session waiting on plan approval now shows the Approve & run / Comment tray on iPhone, web, and the Windows/Linux desktop, so the one decision that unblocks the turn no longer needs the Mac. Send is held while the plan is parked, and Comment on an older host dismisses cleanly instead of leaving an unsendable draft (#1630)
- The worktree +/- diff counter now lives on the session header on iPhone and the mobile app, so you can see the change size with the session open, not just from the list (#1631)

## Fixes
- Starting a session from the phone works again: creates no longer post a cloud sidebar key or another machine's path, both hosts rematch the repo by identity, and an ordinary local create can never silently clone a fresh copy instead of using your working tree (#1631)
- Stop now interrupts a send stuck retrying against a flaky connection, on iPhone, web, and the desktop, while queued prompts keep their order (#1631)
- Attaching a file can no longer freeze the whole Mac app. A wedged network volume used to hang the file picker service and beachball Continuum until reboot; the picker now probes mounts first, opens as a sheet, and offers Eject or Open Anyway with the volume named instead of hanging (#1632)
- Codex accounts on weekly-only plans no longer show a phantom "5h session" gauge at 0% on any surface: menu bar, Usage tab, iPhone, Watch, widgets, desktop tray, and remote Linux hosts all hide the rail until the plan actually has a session window again (#1628)

## Docs and site
- 66 new guides across gateway, spend, and inference topics, 8 comparison pages, and the first interactive tools on continuumcode.ai (#1626, #1627)
- The Claude Pro limits guide now carries the dated Claude Code weekly +50% extension through 31 August 2026, and the guides index pins the most-searched how-tos (#1633, #1634)
