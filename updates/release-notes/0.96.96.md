# 0.96.96

If your Claude account stopped showing up on some of your devices, this release fixes it. The command line is also redesigned.

## Fixes

- Provider accounts sync properly again. Some people saw a real Claude account quietly stop appearing on their other devices: hosts were republishing rows that came back from the cloud, the list grew until it hit its ceiling, and genuine accounts were pushed out. Hosts now publish only the credentials they actually hold, placeholder rows are never created, and existing accounts are repaired on upgrade. (#2035)
- Fewer failed requests. Connections were being reused a moment after the server closed them, which returned an error roughly 94 times a day. (#2034)

## Features

- The terminal app has proper chrome: a header carrying the session, provider and model, themed rails and palette, and a key bar that still fits at 80 columns. One theme drives chrome, markdown, syntax and diffs, with matched light and dark pairs you can cycle with `T`. (#2033)
- Markdown, diff and pull-request panes render as panes rather than raw text, and the composer is bottom-docked and sized by what it displays, so pasting text that looks like chrome no longer loses your cursor. (#2033)
- Send and stop follow an explicit lifecycle instead of guessing, so a delayed reply can no longer land as a cancelled turn. Esc always clears a pending request and restores your draft. (#2031)
- The host fences turns by identity and bounds what it writes into a terminal session, so a slow or oversized write cannot bleed between turns. (#2031, #2032)
