# Continuum 0.65.1

Mesh connections that stay connected, a monochrome Continuum mark that fits the tray, and a
batch of dogfood polish across Chat, Code, and Settings on iOS and Mac.

## Fixed

- **Your devices stay connected.** iOS mesh connections now persist and recover on their own
  instead of getting stuck "handshaking" — no more re-selecting a device and hoping it
  connects. A watchdog gives up on a dead rendezvous and reconnects cleanly. (#1219)
- **Every device is selectable.** The Devices list is now grouped into Available and Other,
  with your Macs first and hosts sorted by session count. Windows and Linux hosts show as
  connected and can run sessions directly — pick any available device from New Session. (#1219)
- **A Continuum mark that fits.** The Continuum provider glyph is now a monochrome mark that
  matches the app icon, sitting alongside Codex, Cursor, and Grok in the model tray instead of
  a colored chip. (#1219)
- **Chat, Code, and Settings polish.** Full Cursor model catalog in New Session, Continuum
  hosted inference shows only when you've enabled it, Code rows carry Mac-parity git branch/PR
  icons, and a round of Chat/Settings/Usage cleanup from dogfooding. (#1221)

## Under the hood

- **Security headers restored on the web.** continuumcode.ai now sends clickjacking and HSTS
  protection (X-Frame-Options, CSP frame-ancestors, Strict-Transport-Security) on every
  response — these were dropped when the backend moved to the self-hosted box. (#1220)
- **Web release points at the live backend.** `release-web.sh` now forwards to the box deploy
  instead of the retired Cloudflare Worker path. (#1220)
