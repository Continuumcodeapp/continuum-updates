# Continuum 0.59.0

A big quality release: twenty fixes and features focused on making the Code tab honest, resilient, and pleasant — queued messages that never get lost, sessions that survive app restarts gracefully, and a sidebar that does what you expect when you archive work.

## New

- **Rich session-completion notifications.** Instead of a bare "a session finished," notifications now say which agent, in which repo, how long it ran, and lead with the same first-message summary you see in the sidebar. (#991)
- **Attachment chips on queued messages.** A queued message with an image or file now shows the same chip you see in chat — icon and filename — instead of a vague "1 attachment." (#988)
- **Archiving selects the neighbor, not the top.** Archiving a worktree now takes you to the worktree directly below it (or above, if it was last) instead of yanking you to the top of the sidebar. (#989)
- **Inherit a sibling tab's context.** The option to seed a new Code draft tab with a previous tab's transcript digest is back. (#975)

## Fixed

- **Restarting the app no longer strands your sessions.** Resumed sessions reconcile their pending messages properly — no more eternal "Sending…" on a message that actually went through, and the transcript shows what you typed instead of internal hand-off text. While a restarted session spins back up you'll see an honest "Resuming session…" instead of silence. (#994)
- **The daemon can no longer be permanently disabled by accident.** A leftover test flag could keep the Sessions daemon off across every launch and reboot, with only a misleading "restart" hint. The app now self-heals that state on launch. (#993)
- **Sending looks like your message, instantly.** The sending state renders as the exact settled message bubble — no dashed placeholder, no spinner chrome, no layout jump when the model starts. (#990)
- **Queued messages survive quitting from any tab.** Queued sends persist to disk the moment you queue them and flush on quit even when you're on the Chat or Usage tab. Restored messages wait for your confirmation — nothing auto-fires. (#986)
- **Steering Fable mid-turn works.** "Send now" on a queued message while a Claude SDK turn runs now interrupts cleanly and delivers your steer as a fresh turn instead of stranding the composer. (#984)
- **Claude turns collapse when they finish.** Completed turns no longer stick expanded due to a stale state race. (#987)
- **PR confetti fires every time.** The celebration no longer disappears for most PRs — and the review pane's Create PR button celebrates too. (#985)
- **Turn timer shows total time.** The working timer no longer resets to zero after background-task waits, on Mac and iPhone. (#992)
- **Archived branches stay archived.** An archived branch could resurrect as an un-hideable sidebar row; it now disappears and stays gone (still visible under Archived). (#983)
- **Sidebar diff badges stay fresh.** The +N −M badge no longer strands stale on idle worktrees. (#980)
- **Worktree rows always clickable.** Rows for repos under ~/Downloads (and other protected folders) no longer go dead after you click away. (#978)
- **Bursts of edits collapse to one row.** A model shaving a file line-by-line no longer floods the transcript with a dozen identical "Edited" rows — they group into one expandable row. (#979)
- **Sidebar cable animates only after you send.** New sessions no longer pulse like they're working before the first message. (#977)
- **Re-log in on secondary accounts.** Secondary Claude/Codex accounts always offer a re-login button, so an expired session token is a one-click fix. (#976)
- **Codex sessions start reliably.** A working Codex install could be reported as missing when the app was launched from the Dock (thin PATH); the preflight probe now checks the same way sessions launch. (#974)
- **Create PR feedback stays in its worktree.** The transient "Queued" state no longer bleeds onto other worktrees' title bars. (#982)

## Under the hood

- Session-completion notification copy is built by a shared, unit-tested helper. (#991)
- The sending bubble is a single shared component between chat history and the pending strip, so the two can't drift apart again. (#990)
- Test tooling now disables the daemon with a process-scoped environment variable instead of a persisted flag. (#993)
