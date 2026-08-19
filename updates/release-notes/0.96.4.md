# Continuum 0.96.4

## Fixes
- Creating a session no longer beachballs the Mac app for about a minute: the worktree reclaim scan was walking every path on the main thread, so the setup trail sat on "Creating worktree 0.0s" until it finished. The scan moved off the main thread and session setup now completes in seconds (#1613)
- Collapsing a menu-bar popover keeps you in the app you were using. Clicking a gauge from Chrome and clicking it again no longer drops the whole Continuum dashboard on top of your work (#1616)

## Docs and site
- The Claude Code limits guide now explains Claude Fable 5 properly: how to select it, the 20 July 2026 plan split, and why the 50%-of-weekly-pool rule is not extra capacity (#1615)
- Claude Sonnet 5 pricing is corrected everywhere to the permanent $2 / $10 per million tokens. Anthropic cancelled the 1 September increase to $3/$15, so the intro-price framing and the projections computed at the old future rate are gone (#1617, #1622)
- The three Claude pricing guides now carry distinct titles instead of competing for the same searches (#1617)

## Under the hood
- Fresh App Store screenshots captured from the shipped build, plus a fastlane `upload_metadata` lane so the store listing actually ships with the binary (#1618, #1619, #1620)
