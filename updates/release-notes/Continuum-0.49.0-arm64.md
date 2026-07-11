# Continuum 0.49.0

A Code-tab and Chat polish release: inline diffs with colored file chips, near-real-time PR status in the sidebar, scrollable spawn terminals with native colors, smoother sending, and a broad sweep of transcript and composer fixes.

## New & improved

- **Inline diffs & colored file chips.** Edited-file chips in the transcript are now color-coded by file type and expand to an inline diff preview on click - see exactly what changed without leaving the chat. (#626)
- **Live PR status in the sidebar.** Per-branch PR state (open / draft / merged / closed), review buckets, and repo PR counts refresh in near-real-time from GitHub instead of going stale. (#635)
- **Scrollable spawn terminals with native colors.** Spawn-grid terminal tiles now scroll properly (TUIs and scrollback) and render native ANSI colors that match your system appearance. (#629)
- **Spawn grid reclaims space.** Closing a spawn tile compacts the grid to the next layout so the remaining live terminals grow to fill the pane, and tiles redraw cleanly on resize. (#631, #633)
- **Smoother sending in Chat.** Your message appears the instant you send with a clean pending state, and the transcript stays pinned to the latest as you send. (#630, #625)
- **More responsive Code tab.** The active worktree stream lights up immediately on send, the loading animation starts the moment you hit send, and workspace tab controls show a pointer cursor on hover. (#619, #618, #621)
- **Small touches.** A hover affordance on the Create PR titlebar control so it reads as clickable. (#627)

## Fixes

- **Transcript rendering.** Fixed a blank transcript after selecting a worktree, a blank-bottom scroll-recovery glitch, and the placement of the hover-to-copy button on your own messages. (#623, #634, #624)
- **Composer.** HTML drag-and-drop attachments work again, and the redundant "expand editor" action was removed from the tools menu. (#620, #628)
- **Chat grouping.** Model-response command runs now group cleanly into a single row. (#622)
- **Under the hood.** Per-turn tool-id dedup in the ACP path is now bounded to a single turn. (#632)

Ships build 262 for Mac (signed Sparkle feed).
