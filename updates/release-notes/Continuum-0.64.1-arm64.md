# Continuum 0.64.1

A polish-and-reliability pass across every surface: your safety checkpoints can no longer
corrupt a repo's git index, GitHub connect stops reporting false failures, Grok's queue
gets a real "send now," attachments keep their human names, iOS scrolling and keyboard
handling feel native, and the web and desktop apps close a long list of gaps against the
Mac app.

## Features

- **Grok "send now" while a turn is streaming.** Queued follow-ups can interrupt the
  current Grok turn and send immediately — same steer flow the other providers use, with a
  guard so a still-stopping turn keeps your draft queued instead of erroring. (#1153)
- **Attachments keep their real filenames.** Staged files show as `PR instructions.md`
  instead of a UUID — in chips, document tabs, and the prompts agents read — with
  collision-safe, traversal-proof sanitization. (#1155)
- **Web + desktop look and behave like the Mac app.** A large parity pass across chat,
  cowork, code, usage, settings, and onboarding — plus a pixel-diff tooling gate to keep
  them aligned. Three Settings toggles that previously saved but did nothing now control
  their real behaviors, and the desktop tray defaults now match the Mac (Gemini and
  signed-in OpenCode gauges on by default, with a fallback tray item so the app never
  becomes unreachable). (#1156, #1166)
- **Smoother iOS.** Native rubber-band scrolling with keyboard swipe-dismiss and
  edge-swipe back, gentler streaming-transcript follow, better composer and safe-area
  spacing, richer Cowork scheduling and held-run cards, and a rebuilt Watch-app setup flow
  that shows real progress. (#1154)

## Fixed

- **Safety checkpoints can't corrupt a repo anymore.** Recovering from a stale
  `.git/index.lock` now proves no live process holds the lock (30s age floor + open-file
  check + identity recheck) before removing it — a lock held by a running git operation is
  always left alone. (#1152, #1166)
- **GitHub connect no longer reports failure after succeeding.** The OAuth fallback waits
  for a real delay instead of racing your install in a second tab, a replayed callback tab
  now shows "GitHub connected" when the connect actually worked, and a malformed GitHub
  response can no longer mark your installations revoked. (#1165, #1166)
- **The chat provider tray is decluttered** — the account picker moved out (account
  pinning lives in the Code composer chip). (#1161)
- **The expanded right pane opens on To-Do's**, not Plan. (#1163)
- **Grok's effort dial matches what grok-4.5 actually accepts** (low · medium · high)
  across Mac, web, and the Go daemon — which now really passes your choice to the CLI,
  including headless chat sessions that previously ignored it. (#1151, #1166)

## Under the hood

- Desktop CI builds fixed (duplicate afterPack key) and the parity scorer recalibrated to
  a meaningful strictness. (#1159, #1166)
- Cloud DB upsert arbiters repaired (workspace mirror shells + usage snapshots). (#1160, #1162)
