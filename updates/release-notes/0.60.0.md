# Continuum 0.60.0

Pairing gets radically simpler: **signing in is pairing.** Your Mac and iPhone find each other through your account — no QR dance — and the sub-agent timer, a stuck sleep banner, and a batch of copy polish round it out.

## Features

- **Sign in on both devices and they just connect.** Your Mac self-enrolls when you sign in, your iPhone and iPad appear as controllers automatically, and every device on your account shows up in one list you can name, approve, and revoke. Each controller still asks for a one-tap approval on the Mac the first time it connects, so the trust boundary is unchanged. QR pairing moves to an Advanced fallback for signed-out or offline setups. (#1036)
- **More resilient connections.** Devices now report an honest online/offline heartbeat, the relay proactively reconnects on wake and network changes and rotates endpoints if one is unreachable, and push notifications ride the account mesh. (#1036)
- **The sub-agent working indicator matches the rest of the app.** A running sub-agent now shows the same terra-cotta data-stream and timer as the session footer, instead of a mismatched spinner. (#1027)

## Fixed

- **The "Mac sleeping soon" banner clears on wake.** It could latch during a low-battery sleep and then stick around at 100% battery; it now releases the moment the Mac wakes. (#1021)
- **Correctly-added models stop being flagged as mispriced.** The model-onboarding checker now resolves pricing exactly the way the running app does, so a valid model (e.g. Grok 4.5) verifies instead of false-failing. (#1030)
- **Cleaner copy throughout.** Em dashes are replaced with plain hyphens across every user-facing surface for a more natural read. (#1035)

## Under the hood

- First full test run of the relay resilience layer (endpoint rotation, per-IP edge rate limiting, a bootstrap init-race fix) — relay + cloud suites green; a real reconnect bug (the pairing bundle re-sent after a frameless drop) was caught and fixed. (#1036)
- `relay.continuumcode.ai` is live as the primary relay endpoint, with the previous origin kept as an automatic fallback.

Ships build 298 for Mac (signed Sparkle feed).
