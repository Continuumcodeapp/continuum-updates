# Continuum 0.47.0

A broadcast + multi-provider polish release: focus a single answer in a broadcast, an effort tray that matches each provider, a quieter Code tab, and a daemon-pairing reliability fix.

## New & improved

- **Focus one answer in a broadcast.** A new "I prefer this response" mode expands the column you like and tucks the others into tappable rails — fully reversible, and it never archives or changes your transcript. (#590)
- **An effort tray that fits the provider.** The reasoning-effort dial now offers only the levels a given provider actually supports (Grok no longer sees a "max" it would reject), and switching providers safely clamps your effort to a level that provider accepts. (#593)
- **A clickable empty-state composer.** The attach button and the repo/account/location pickers on the empty-state composer get a hover highlight and a pointing-hand cursor. (#589)

## Fixes

- **A quieter Code tab.** Changing model, provider, or effort on the Code tab no longer pops a toast every time — the switch just happens. (#591)
- **Pairing actually connects.** The Mac daemon now binds its port for real (and falls back to a free one) before advertising it, fixing the case where a freshly paired session couldn't reach the daemon — the "model not attached" symptom. (#594)
- **Matching broadcast pill on iOS.** The iOS broadcast model pill now matches the Mac multi-model pill. (#592)

Ships build 259 for Mac (signed Sparkle feed). The iOS app ships the same broadcast and multi-provider improvements via TestFlight.
