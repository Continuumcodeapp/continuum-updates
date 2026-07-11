# Continuum 0.42.3

A focused fix release: cross-vendor model switching now actually switches the running agent, plus a smoother spawn button and updater.

## Fixes

- **Cross-vendor model switch actually switches.** Switching a running session from one vendor to another (e.g. Claude → Codex) now restarts the agent on the new vendor's runtime instead of just changing the chip in the UI - the next message really goes to the model you picked. (#514)
- **Smoother updater progress bar.** Fixed a flicker where the update-download progress bar could flash empty or slide off-screen between progress callbacks. (#515)
- **Aligned empty-state chips.** The meta chip row under the empty-state composer now lines up cleanly with the composer box. (#511)

## Spawn button

- **Split Spawn action.** Clicking the Spawn sidebar row now one-click-spawns your default grid; the trailing "+" opens the config tray to pick count and agent mix. (#513)
- **"+" hover affordance.** The Spawn "+" lights up with a subtle wash when you hover it. (#512)

Ships build 250 for Mac (signed Sparkle feed), with iOS/watchOS to TestFlight.
