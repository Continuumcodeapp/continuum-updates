# Continuum 0.57.14

A polish release for the Code composer and session sidebar - slash commands and mentions are easier to use, the live data-stream animation stays smooth with many sessions, and a batch of Mac and iOS composer fixes.

## Fixed

- **Slash-command turns read as `/command`, not the whole skill doc.** Invoking a skill like `/pr-land` now shows just `/pr-land` in the transcript instead of the entire expanded skill document. (#838)
- **The slash / @-mention picker no longer covers what you're typing.** The completion palette opens directly above the composer input, so the text field stays visible while you pick a skill or mention. (#838)
- **Shift+Enter breaks the line in the composer** instead of sending. (#837)
- **The sidebar data-stream cables keep animating** with many active sessions, and stay live while a session is monitoring or waiting. (#835, #836)
- **Smooth, calm scroll to the newest message** on send and when creating a PR. (#834)
- **iOS composer cleanup:** usage vendors fold into a single toggle, the stuck stream cable is fixed, and session controls moved to the composer. (#833)
- **User bubbles no longer show Claude Code's synthetic image-coordinate hint.** (#832)
- **The first-send prompt shows while the worktree is still provisioning**, so you're not staring at an empty pane. (#831)
- **Cleaner chat history:** mid-turn narration collapses and completed turns fold to the final answer by default. (#830)
- **iOS: autocorrect no longer mangles composer typing.** (#829)
- **⌘V image paste works again after switching sessions.** (#828)
- **Live, light repo drag-reorder in the Code sidebar** that can reach the bottom of the list. (#827)

Ships build 285 for Mac (signed Sparkle feed).
