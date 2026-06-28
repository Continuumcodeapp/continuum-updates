# Continuum 0.57.8

Connecting remote devices over Tailscale is faster, more reliable, and now fully one-click for Macs.

## New

- **One-click remote Mac setup.** When you connect a Tailscale Mac that doesn't have Continuum yet, setup now downloads, installs, and starts it for you automatically — then continues registration. No more manual install step before connecting a Mac. (#798)
- **Instant "Add Tailscale device" picker.** The picker opens immediately and scans your tailnet in the background, and the device list is cached so reopening is instant. Tailscale lookups are also time-bounded, so a stuck or slow Tailscale never hangs the sheet. (#797)

## Fixed

- **More reliable remote-device installs.** Visible installs run over a real terminal with the **Done** button enabled only once the command actually finishes, so you can't dismiss setup mid-install. Linux setup now fails with clear, actionable guidance if a device never returns its pairing token, instead of silently stalling. (#799)

Ships build 279 for Mac (signed Sparkle feed).
