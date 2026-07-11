# Continuum 0.57.3

A feature-and-reliability release: drive interactive remote sessions across your devices, open any Markdown doc from a new Documents sidebar, watch OpenCode and secondary-Claude usage as real gauges, cut token spend with Ponytail, and a long run of fixes that keep busy Code sessions, Claude background turns, voice, and paste behaving.

## New

- **Interactive remote sessions across your devices.** Start and drive three-way remote agent sessions over Tailscale - your Mac, iPhone, and a remote host stay in sync inside one live session. (#756)
- **Continuum Cloud - org usage.** A new org usage platform on continuumcode.ai gives teams a shared view of agent usage and spend across accounts. (#757)
- **Open `.md` and other docs from anywhere.** A new Documents section in the sidebar lets you open and read Markdown (and other docs) from any folder on your Mac - not just files inside a workspace. (#753)
- **OpenCode usage as first-class gauges.** OpenCode Go usage now shows up alongside your other providers as live gauges in the menu bar, the popover, and the Usage tab, so you can see spend at a glance. (#754)
- **Ponytail token-saver in Save Costs.** Settings → Save Costs adds Ponytail, a token-saver that trims what gets sent to the model to bring your costs down. (#749)

## Improved

- **Honest secondary-Claude status and live usage.** A secondary Claude account now shows a true signed-in state with its own live usage gauge, instead of misreporting as logged out. (#755)
- **Busy Code sessions stay smooth.** Running 5–10 active Code sessions at once stays responsive, and the oldest session keeps reporting its liveness correctly rather than going stale. (#743)
- **Claude background turns stay live.** Turns kicked off by background tasks no longer appear to stall - the live turn keeps streaming until it's actually done. (#742, #748, #744)
- **Quieter token handoff for secondary Claude accounts.** A secondary Claude account's terminal now receives its token without triggering a keychain permission prompt every time. (#750)
- **Markdown tables render in chat.** GitHub-flavored Markdown tables in chat now render as real tables instead of raw pipes. (#758)
- **Provider auth and launch fail closed.** Provider auth, launch, usage, and spawn now fail closed instead of falling back silently, so a misconfigured account never bills the wrong subscription. (#758)

## Fixed

- **Paste images consistently across Code and Chat.** Pasting an image from the clipboard now works the same way in both the Code and Chat composers. (#741)
- **Voice no longer hijacks ⌘V; double-tap restored.** Pressing ⌘V to paste no longer starts voice input, and the Left-Option double-tap to trigger voice works again, with a cleaner voice-permission prompt. (#738, #745)
- **Cleaner terminal and command output.** Spawn-grid terminals stop garbling full-screen (TUI) output, and Codex shell actions are broken out individually instead of being hidden behind a "Ran N commands" roll-up. (#746, #740, #735)
- **Draft reply hidden until you send.** A draft's replacement session no longer flashes on screen during the first send, and hiding the draft tab now works regardless of what's selected. (#747, #752)
- **Code-tab model chip stays in sync.** The model chip on the Code tab now matches the runtime when you spawn or switch sessions. (#736)
- **Clear message when Grok steer is unavailable.** Instead of failing silently, Continuum now tells you when steering Grok isn't available. (#739)

Ships build 274 for Mac (signed Sparkle feed).
