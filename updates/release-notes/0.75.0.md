# Continuum 0.75.0

Dictation on iPhone goes hands-free — it stops when you stop talking — a double
back tap can toggle it, and the public changelog got its lost history back.

## What's new

- **Dictation stops when you stop talking.** Start Continuum Voice from the
  Action Button or Back Tap and just speak — when you go quiet, the turn ends
  and your words are delivered, no second press needed. The pause length is
  tunable in Settings → Voice (1.5s / 2.5s / 4s), and it fails safe: if the
  audio signal isn't usable, it simply waits for your manual stop. (#1396)
- **Double Back Tap toggles voice.** Set up **Settings → Accessibility → Touch →
  Back Tap** with the Continuum shortcut and two taps on the back of the phone
  start dictation, two more stop it — even from a cold start. The new setup
  cards in Settings → Voice walk through it. (#1396)
- **See your words before they land.** The Continuum keyboard now shows a live
  transcription pill — waveform while you speak, then the finished text animates
  in before it's inserted into the field, matching the Mac's dictation overlay.
  The old keyboard mic button is gone; the gestures replace it. (#1396)
- **The docs changelog remembers every release again.** The public changelog at
  continuumcode.ai/docs/changelog had silently lost every release between 0.57.1
  and 0.73.0. The full 94-release history is restored, and the release pipeline
  now merges into the published feed instead of overwriting it — with a guard
  that refuses to publish if history would be lost. (#1393)
- **Download links point at current builds.** The download page's Windows,
  Linux, and CLI links had drifted 11 versions behind; they now track the
  latest release, the code-signing FAQ matches reality (macOS is notarized,
  the Windows installer is signed), and the new docs pages are submitted for
  search indexing. (#1394)
- **iOS Settings drops the non-functional Add funds section.** Top-up isn't
  available for most accounts yet, so the card is hidden on iPhone (native and
  Expo) until it works — behind a one-line flag for when it returns. (#1392)

## Under the hood

- Native Google Analytics finally records in release builds — the GA4 API
  secret now ships with the app instead of living only on one dev machine,
  bringing the Apple apps in line with web, desktop, and mobile. (#1395)
- Dictated text can no longer land in the wrong text field: moving focus during
  the keyboard's reveal now revokes the pending insert instead of re-anchoring
  on whatever field you tapped next. (#1396)
- Voice endpoint detection adapts its threshold to the speaker, decays after
  loud transients, re-anchors on clock changes, and never auto-stops without
  speech evidence. (#1396)
