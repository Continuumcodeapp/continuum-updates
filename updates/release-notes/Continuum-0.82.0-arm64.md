# Continuum 0.82.0

## What's new

- **Hit a 5-hour or weekly limit? Continue the same session on your other account.** Claude and Codex limit failures now offer a "Continue with <account>" action that resumes the exact session — same model, same reasoning effort, same mode, same repo and conversation, and your failed prompt is re-sent for you. Only the credential changes, and only genuinely different, signed-in accounts are offered. Works on Mac, iOS, web, and Linux/Windows hosts. (#1457)
- **Auto mode now starts on Continuum-hosted inference — and Cancel really stops the work.** Hosted-only setups no longer see "Auto run couldn't start", Auto's Cancel and timeouts stop the actual child model run instead of just the coordinator (no more invisible quota burn), and if a child refuses to stop you're told exactly which session to close. Relay reconnects from a fresh browser tab are also reliable now. (#1458)
- **Open a plain folder and just start working.** A Local session on a folder with no git repo used to dead-end the safety checkpoint; now Continuum quietly runs `git init` (with an empty base commit — your files are never staged for you), tells you once, and Rewind genuinely works there. Home folders, other users' homes, and whole volumes are refused, on every host. (#1450)
- **⌘Enter inserts a line break instead of sending.** Paste multi-line text, hit ⌘Enter, and the caret moves to the next line — in every composer on Mac, web, and desktop. Bare Enter still sends; the cheat sheet and shortcut settings reflect the change. (#1455)
- **Links in transcripts finally look and act like links.** Blue, underlined, clickable, with hover and keyboard-focus feedback — including bare URLs inside bold or italic text that used to render inert. Correct contrast in light mode on every surface. (#1451)
- **Connect GitHub no longer yanks the repo picker out from under you.** Members finishing an App install get a "Finish on GitHub" button instead of a surprise navigation 45 seconds in, and the install flow works for every org member, not just the app owner. (#1449)
- **Free tier, opened up.** Bring-your-own-key models are free with no gate, and hosted access gets three trial rungs so you can start without a card. Hosted Opus 4.8 is retired in favor of the current lineup. (#1447)

## Fixes and under-the-hood

- Two Code tabs in the same worktree no longer bleed each other's prompts and replies — every tab is pinned to its own transcript, on Mac and Linux/Windows hosts. (#1453)
- Fixed a Mac crash when model/context shortcut popovers fired while several composers were mounted; those shortcuts now route to exactly one composer, and ⌘Enter/⌥Enter can no longer send a hidden session's draft. (#1456)
- The OpenCode menu tab shows your real 5-hour, weekly, and monthly limits again instead of dead $0.00 spend tiles. (#1454)
- Voice dictation's global toggle is now opt-in and configurable in Settings. (#1445)
- Native design polish across Mac, iOS, and web, and the menu-bar-only mode can no longer strand the app out of the Dock on reopen. (#1444) (#1448)
- Admin: comped accounts show their granted tier instead of "Free". (#1446)
- Add-Repo error messages are now identical on Mac and iPhone, with actionable recovery steps. (#1452)
- Hardened credential storage against a spoofed test-mode launch, account-switch spawns can no longer inherit another account's credentials from project env files, and cross-host handoffs verify the source actually stopped before archiving it.
