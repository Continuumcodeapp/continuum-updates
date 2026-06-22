# Continuum 0.43.0

A Chat- and Settings-focused release: per-provider session defaults, a way out of a stuck turn, and a cleaner, calmer chat surface — plus a batch of fixes across the composer, worktrees, and the Voice picker.

## New & improved

- **Per-provider session defaults.** Settings now has default effort + permission-mode columns for each provider, so new sessions start with the reasoning effort and permission mode you actually want instead of a one-size-fits-all default. (#529)
- **Stop + Retry on a stuck turn.** When a chat turn hangs, Stop and Retry controls now fade in on the loading indicator so you can interrupt or resend the last message without abandoning the chat. (#533)
- **Live updater rail meter.** While an update downloads, the updater toolbar pill turns into an inline rail meter with a live percentage instead of a bare spinner. (#527)
- **Calmer, flatter chat.** The working-stream indicator is now borderless to match the Code tab, and assistant replies sit flush on the black canvas with the bubble background removed. (#532, #534)

## Fixes

- **Worktrees no longer open blank.** Opening a worktree session that rendered an empty transcript now refreshes and shows the conversation instead of a blank pane. (#528)
- **Copy button stops flickering.** The chat message copy button no longer flickers on hover and now shows a pointing-hand cursor. (#530)
- **Long composer text wraps.** Long text typed into the Chat composer now wraps and grows the field instead of being clipped on one line. (#531)
- **Voice model picker is ordered sensibly.** The Voice model picker now lists the active model first, then recommended, then the rest. (#535)

Ships build 252 for Mac (signed Sparkle feed).
