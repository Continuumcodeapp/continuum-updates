## What's new in v0.96.17

Mesh reliability, round two. Every item below was traced from the 24/7 diagnostics shipped in 0.96.16 (phone export, Mac host log, relay per-session log, box database) and fixed at the root.

### Fixes
- **No more phantom "streaming" sessions.** After a host restart, sessions whose agent process died with the app came back as `running` with the data-stream animation on the phone (12 such sessions on one Mac). Hosts now reconcile every running session against a live runtime at startup and every 60 s, mark the dead ones paused with an explicit "not streaming" flag, and the iOS/web/Expo clients stop animating any session whose last event is older than 30 minutes.
- **Second Claude account no longer vanishes when the Mac link drops.** Usage keeps the last live envelope (with an "as of HH:MM" marker) instead of falling back to the empty cloud snapshot.
- **6-minute reconnect after a host restart is gone.** The relay now tells the phone when its host peer leaves (`peer-left`), so the phone remints immediately instead of cycling its own socket every 40 s; hosts re-dial the controller sessions they were serving before relaunch.
- **Resume-from-background 412 ladder is gone.** A dead rendezvous (404/410/412) triggers an immediate host-scoped remint on iOS and Mac, and the relay keeps a reinitializable auth stub for controller sessions after idle eviction.
- **Host-control renewal no longer tombstones a session the host just joined.** Renewal needs real, spaced dial failures; the old session gets a 120 s grace instead of an instant evict.
- **iPhone diagnostics finally upload.** The phone's own device identity failed to persist to the Keychain (a stale item from an earlier build shadowed the write), so it re-enrolled every 35 s and never had a device id. Persistence now upserts, logs exactly which step failed, keeps a transient identity meanwhile, and backs off instead of hammering the backend.
- Offline hosts are retried on a 60→120→300 s cadence instead of every 20 s; the relay keeps one queued push per controller.
- Diagnostic log retention honours the 30-day floor, and each event reaches the unified log once instead of four times.

### Also in this release
- Projects in the web Code sidebar now collapse and expand, matching the Mac app. A repo you fold stays folded across reloads, opening or starting a session unfolds its project, and Cmd+1..9 jumps skip hidden rows. The count badge, gear, and new-session buttons are always visible on every project row instead of appearing on hover
- Add project now works against a Mac host: the web and desktop Add-Project menu (clone from GitHub, quick start, open local folder) no longer shows "Onboarding needs a newer host" on an up-to-date Mac. The Mac serves the same register route as Linux and Windows hosts, refuses sensitive system folders, and returns the existing project when a folder is added twice
- The Connections overlay lists every supported AI provider (Claude, ChatGPT, Gemini, Cursor, OpenCode, OpenRouter, Grok, Z.ai Coding) and detects the ones already connected on your host or account, showing a green Connected state instead of asking you to connect what already works
- Connecting GitHub from the new Connections overlay handles an app installation made directly on github.com: the Connect pass adopts the existing installation instead of dead-ending, and a "Finish authorizing" fallback appears when GitHub skips the setup screen
- Auto-discovered project icons now persist in the browser, so the sidebar shows them immediately on the next visit and on projects whose host is asleep
- The New Session device picker on the web now defaults to Continuum Cloud and lists every connected device on your account by name and platform; an explicit device pick sticks across refreshes and relaunches
