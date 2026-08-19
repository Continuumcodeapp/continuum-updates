# Continuum 0.96.3

## Features
- Chat can now open the documents it talks about: a file path in an assistant reply becomes a preview action on every client — the desktop Preview pane, the iOS sheet, the web Preview tab — and the artifact transfers behind it are bounded and hardened against symlink swaps and oversized files (#1608)
- Grok gains an Extra high reasoning rung on every effort picker — Mac, iOS, web, and the Linux/Windows agent — and new Grok sessions start there, matching how Claude and Codex seed their top rung (#1601)
- Continuum-hosted models now honor their real limits: all 16 hosted models publish verified context windows and output ceilings instead of a blanket 8K output cap, long tool runs are no longer killed at 10 minutes, and headless sessions disable the TUI-only question tool that could strand a turn forever (#1606)

## Fixes
- The Mac updater no longer strands on "Installing update" when you decline the quit: the popover now offers Quit & Install, retries are bounded, and a stuck install self-heals instead of scrolling forever (#1607)
- The Code composer's + button opens the file picker again, and picked files keep their real names on the chip instead of a staging UUID (#1612)
- Adding an MCP server from Settings works again in packaged builds, and a rejected save now shows the host's actual reason instead of "Couldn't save that server." (#1609)
- A subagent's permission prompt now reaches your approval card instead of silently killing the turn with a bogus "provider failing upstream" error — and rejecting one subagent no longer discards its siblings' prompts (#1610)
- The transcript reading window holds still while you scroll, and "Show earlier messages" stays expanded once you've clicked it (#1599)
- The sidebar's data-stream animation stops when a session ends or is interrupted, on every path including a wedged teardown (#1603)
- Cursor gauges match cursor.com: sub-1% usage no longer reads as 0%, the lanes carry Cursor's own names — Cursor Models and Other Models — and the extra billing copy other providers never had is gone from the usage cards (#1604, #1611)
