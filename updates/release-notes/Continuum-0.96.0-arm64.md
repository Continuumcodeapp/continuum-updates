# Continuum 0.96.0

## Features
- Environment variables now travel with the repo: each account gets a per-repo env database in the cloud, so a project's keys follow you to whichever device you open it on instead of living on one machine (#1587)
- The web app now carries the Mac's two-level repo/worktree sidebar, so a repo with a dozen worktrees reads as one project with branches under it instead of a dozen unrelated rows (#1581)
- Code review on the web matches the Mac: the review pane rotates through files the same way, and To-dos are there as a first-class pane instead of Mac-only (#1582)
- The Mac's PR review verbs work on the web on both host types, so you can approve, request changes, and comment without switching to the Mac (#1593)
- Review comments can now be authored from the Apple clients against Linux and Windows hosts, because the agent serves the comment endpoint they need (#1596)
- Diagnostics on the web gained an audit-log viewer on both hosts, so you can see what an agent actually did without reading a file on the machine (#1594)
- The Mac's keyboard shortcut set now works on the web, so the muscle memory carries across (#1591)
- Menus, buckets, and grouping on the web match the Mac's, down to where each item sits (#1590)
- The composer intercepts pasted secrets before they reach a prompt, and context chips show what's actually attached to the turn (#1592)
- Settings and Usage on the web close their last gaps against the Mac reference — the same controls, the same numbers, in the same places (#1583)
- A repo is now the same project on every device, matched by its GitHub remote rather than its local path, so a machine that checked out to a different directory stops showing up as a stranger (#1579)
- To-dos now work on Linux and Windows hosts, not just the Mac: the Go agent emits real todo state instead of an empty list (#1588)
- The web-parity harness runs against a re-baselined reference and covers the Windows desktop surface for the first time, so a gap between clients gets caught before it ships (#1580)

## Fixes
- Two processes can no longer each claim a different managed client id, which had let one machine show up twice (#1595)
- Continuum no longer crashes on macOS 27 when a popover closes (#1573)
- Dropping a file on the composer attaches it instead of pasting its path as text (#1575)
- Hosted OpenCode turns survive past 20-40 minutes: the 1MB completion body cap that killed them is raised and admission is rate limited (#1576)
- The sidebar's streaming animation stops when the turn does, instead of spinning forever on a finished turn (#1577)
- iOS voice input no longer refuses to record because a ghost call is stuck in the system's call registry (#1578)
- A turn that already reported itself unresponsive is not called again, so one dead turn stops turning into a retry storm (#1584)
- Attachment chips show the file's real name rather than the internal staging UUID (#1585)
- Jump-to-latest no longer collapses a long transcript on the way down (#1586)
