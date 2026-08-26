## What's new in v0.96.18

Three fixes traced from today's live logs, all in the mesh/host path.

### Fixes
- **The Mac host no longer dies silently.** Continuum on the Mac exited with SIGPIPE five times in one day (launchd: "exited due to SIGPIPE") — a write to a child process or connection that had already gone away took the whole host down, every relay socket dropped, and the phone showed "Couldn't connect to that device" until someone relaunched the app. The process now ignores SIGPIPE, every child/PTY/network writer handles EPIPE and tears down only its own session, and unexpected terminations leave a breadcrumb in the host log.
- **Dead sessions with a resumable handle no longer show as streaming.** The 0.96.17 reconcile skipped sessions that still had a resumable provider id; 61 such sessions stayed "running" on one Mac. Ownership now means a live process only; the resume id is preserved so the conversation can be revived, and the cloud mirror is republished.
- **Continuum Cloud picks up a repo's GitHub remote automatically.** Choosing a repo that lives on your Mac and switching to Cloud no longer fails with "Continuum Cloud needs a Git repository URL": hosts publish each repo's origin and default branch, and the phone/web resolve it for you. Errors now name the repo or the missing GitHub App install.
