# Continuum 0.57.6

A big UI refresh for starting and managing sessions, a new hands-free dictation mode, and a wave of chat polish and reliability fixes.

## New

- **A floating New Session composer.** The "+" button (and ⌘N) now opens the "What should we build?" composer floating right over your current session, instead of a separate sheet - pick Plan/Code, effort, and a one-click Worktree or Local toggle inline, or just hit Create for an empty session. ⌥-click "+" still does the instant quick-spawn. (#779)
- **Choose Worktree or Local per new session.** New sessions remember a per-repo (and global) default for whether to run in a git worktree or directly in your working copy, with optional file-copy across devices. (#775)
- **Universal voice transcriber.** Dictate straight into whatever app is focused - runs on the on-device Parakeet model by default. (#773)
- **Refreshed Code-tab and Devices look.** Code-tab tabs are now clean primary-nav pills, the Devices settings sheets match the rest of the app, and the repo-header "+" lines up with its sibling buttons. (#780, #778, #777)

## Fixed

- **Long-running tool calls aren't killed anymore.** The harness watchdog no longer cuts off a live, long-running tool call mid-execution. (#770)
- **Instant worktree switching.** Switching from one worktree to another is now immediate, with cleaner single-row selection in the sidebar. (#772)
- **Add Tailscale device actually connects.** The Add Tailscale device tray no longer gets stuck, and "Install & connect" completes. (#771)
- **Smoother Grok steering.** Queued follow-up steer messages now have a clearer, less confusing flow. (#769)
- **Chat polish across the board.** Consistent transcript theming (#768), stable scrolling (#767), correct toast colors in light mode (#766), and better formatting of large messages (#764).
- **Codex commentary stays tucked away.** Codex's running commentary is kept behind the transcript disclosure instead of cluttering the thread. (#765)
- **Cleaner transcript lifecycle.** Polish to how transcripts wind down and how PR completion is reflected. (#776)

## Under the hood

- **Cross-platform analytics.** Mixpanel, Google Analytics, and PostHog are now wired across Mac, iOS, Watch, and web. (#774)
- **Email device-mesh foundation (off by default).** Groundwork for an email-based device control plane, flag-gated off for now. (#763)

Ships build 277 for Mac (signed Sparkle feed).
