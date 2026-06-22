# Continuum 0.44.0

A big workspace release: a new top-effort **Ultracode** mode for Claude, one-click Plan/Code switching with per-provider defaults, automatic retry of failed turns, and a Code-first tab layout — plus a security hardening pass across the agent runtime.

## New & improved

- **Ultracode effort mode for Claude.** Claude sessions get a new top-tier "Ultracode" effort beyond Extra-high — maximum reasoning plus standing workflow orchestration — selectable from the effort chip on Claude-only sessions. (#536)
- **One-click Plan ↔ Code, with your own defaults.** The permission menu collapses into a single Plan/Code pill (Code grants full permissions and auto-trusts the repo), and a new "Your Preferences" section in Settings lets you set the default model, effort, and Plan/Code mode per provider. (#541)
- **Auto-retry for failed turns.** When a model response fails on a transient error, Continuum now retries it automatically with capped backoff and shows inline attempt cards so you can see what happened instead of a dead turn. (#542)
- **Code-first tab order.** The Mac tabs are reordered to Chat · Code · Usage · Settings, with ⌘1–⌘4 following the new layout. (#537)
- **Copy a full answer in one click.** A quiet copy-answer button now appears at the end of every completed turn across all chat surfaces. (#543)
- **Turn-completion notifications.** Continuum can notify you when an agent finishes its turn, with a toggle in Settings and tap-to-open routing straight to the session. (#544)
- **A more useful transcript minimap.** The Mac transcript minimap is now more prominent and expands on hover so you can scan and jump through a long conversation. (#540)
- **Attach an app shot.** The composer can capture the frontmost window — or any visible app window — and attach it to your prompt as a rich preview. (#538)

## Security

- **Agent-runtime hardening (CSO P0/P1).** A security pass closed an agent remote-code-execution path, scrubbed provider secrets from spawned environments, bound end-to-end message authentication, tightened consent handling, and moved pairing tokens to at-rest Keychain storage. (#539)

Ships build 255 for Mac (signed Sparkle feed). The iOS app ships a full Continuum Mobile redesign + on-device voice dictation in this build via TestFlight.
