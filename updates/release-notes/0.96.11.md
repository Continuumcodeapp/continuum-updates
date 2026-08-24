# Continuum 0.96.11

## Features
- The review pane's six flat tabs are now three groups — Tasks, Code, and Terminal — on Mac and web. Each session remembers which leaf you were on per group, the collapsed gutter reopens exactly where you left off, and keyboard and VoiceOver users get real grouped controls (#1653)
- Signed out, the Continuum model rail now shows the same model names, order, and availability as signed in: free and trial models stay usable, paid hosted models show a Sign in action, and the redundant provider prefix is gone from every provider-scoped picker across Mac, iOS, web, and the CLI (#1659)
- Transcripts are now archived permanently with per-page model, effort, and account attribution, and the superadmin Prompts tab reads from that archive with customer, timestamp, and repo tags — sessions survive host offboarding and stay exportable for authorized review. Archive pages are encrypted per member, tenant-bound, and quota-capped (#1652)

## Fixes
- Attaching files on the Mac can no longer freeze the app when a network drive is wedged: drag-and-drop, the file picker, clipboard paste, and in-app browser uploads all run off the main thread with bounded timeouts, and a stuck volume can be force-ejected from the picker (#1650)
- Fenced code blocks render as clean cards with a language header and a per-block copy button that reports success honestly, on Mac, iPhone, and the mobile app — rapid copies and streaming edits no longer leave stale "Copied" states (#1654)

## Under the hood
- App updates are getting dramatically smaller: the Mac app no longer bundles 295 MB of Linux agent runtimes (they download on demand, hash-verified, the first time you add a Linux host) and the release pipeline now produces byte-identical artifacts when nothing changed, so Sparkle deltas shrink from ~257 MB to a fraction of that (#1656, #1658)
- Linking your own provider credentials now emits linked, failed, and revoked analytics events with correct semantics on web and Mac, so BYOK activation is measurable without ever touching credential material (#1657)
- Patched hono, @hono/node-server, and esbuild advisories across the cloud backend and APNS gateway, and the APNS production image now installs from a locked dependency graph (#1655)
