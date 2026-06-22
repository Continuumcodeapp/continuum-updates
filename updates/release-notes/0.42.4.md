# Continuum 0.42.4

A polish-and-fix release for the Code workbench: snappier session starts, a calmer chat surface, and a batch of glitches in the sidebar, activity cable, and transcript that are now gone.

## New & improved

- **Instant New Session.** The New Session sheet now spawns optimistically for every agent — the row appears and is ready immediately instead of waiting on provisioning, so starting work feels instant. (#517)
- **Chat attachments as file chips.** Files you attach in chat now render as tidy file chips instead of raw paths. (#518)
- **Rounder "Jump to latest."** The jump-to-latest control is now a clean round chevron FAB. (#516)
- **Calmer context ring.** Removed the pill background behind the composer's context-usage ring so it sits flush with the composer. (#520)

## Fixes

- **The activity cable stays lit while the agent works.** Trailing usage/diff events could leave the data-stream cable stuck on, or a row could mount before its stream resolved; the cable now tracks the live turn and lights for exactly as long as the model is working. (#519, #523)
- **Model-chip switch after a quick spawn actually switches.** Toggling the model chip right after a quick-spawn no longer loses the race against provisioning — the running agent converges to the chip you picked. (#522)
- **Idle worktree rows keep their name.** A worktree session's name now shows while it's idle, not only while it's active or after you click it. (#521)
- **Stuck "Sending…" bubbles clear.** An acknowledged send that never echoes back can no longer leave a permanent "Sending…" bubble, and the per-turn Preview chip only appears when there's an actual preview to open. (#524)
- **Code sidebar branches stay visible.** A branch row no longer disappears when its session moves from running to done — only archiving removes it. (#525)
- **No more transcript flicker on rollover.** Switching to a rotated transcript file no longer flashes a blank/stale frame. (#526)

Ships build 251 for Mac (signed Sparkle feed).
