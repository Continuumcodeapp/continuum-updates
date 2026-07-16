# Continuum 0.63.3

Continuum now runs beyond the Mac: native Windows and Linux desktop apps with full Code-workbench parity, a cross-platform `continuum` CLI/TUI, and a bundled Go agent. Settings gains a complete provider-authentication manager — see who you're signed in as, sign out, re-authenticate, or edit API keys per provider — and app-owned credentials are stored once and reused across your devices and background refreshes. Plus Code terminals now open as real login shells, and Grok renders its full activity timeline in Chat, Code, and Cowork.

## Features

- **Continuum on Windows and Linux.** A native desktop app for Windows and Linux with full Mac-desktop parity: system tray, managed daemon lifecycle, loopback auth, and all ten Code-workbench rows — terminal resize, checkpoints, worktree rename, session export, GitHub review comments, the keyboard shortcuts legend, Cmd+; sub-chats, the scheduler, a rich Markdown/image/PDF document viewer, and pop-out windows. Ships alongside a cross-platform `continuum` command-line interface and TUI backed by a lightweight Go agent. (#1057)
- **Manage provider authentication in Settings.** A new provider identity panel shows which account each provider is signed in as, with a persisted reveal/blur toggle, and gives every provider its own Sign out, Log in / Re-authenticate, edit API key, and Disconnect controls for both built-in and custom providers. (#1134)

## Fixed

- **App-owned credentials are reused across devices and background refreshes.** Claude and OpenCode credentials are stored in Continuum's device Keychain after the first connection and preferred for background polling, session setup, and remote-host installation — so routine usage refreshes stay non-interactive instead of repeatedly reopening an external key manager. Only definite authentication failures are rejected; newer sign-ins are preserved through stale responses and across relaunches. (#1130)
- **Code terminals open as real login shells.** Terminal tabs — the tab strip, the right review pane, and multi-pane `+` — now launch a plain login shell in the session's working directory (with an enriched PATH so GUI-launched shells still find Homebrew tools) instead of an agent process, and show a home-relative path bar and subtitle. Panes are labeled Shell / Shell 2 / … (#1129)
- **Grok shows its complete activity.** Compatible Grok CLIs route through the ACP transport so Chat, Code, and Cowork render tool calls, command output, edit chips, progress prose, and final replies, with exact provider-session continuity preserved across app relaunches. Older CLIs keep the existing fallback. (#1131)

## Under the hood

- **Sturdier cloud-box release pipeline.** Per-dev-database passwords validate independently, and gaps found during the 0.63.0 box deploy are closed. (#1132, #1133)
