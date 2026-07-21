# Continuum 0.65.3

One-tap Google sign-in on the web, a chat archive you can hide and bring back, a web chat
that now feels Mac-grade, and steadier Code and Chat sessions on iOS when devices come and go.

## New

- **One-tap Google sign-in.** The marketing site now offers Google One Tap — sign in with a
  single click, no password, no redirect detour. (#1244)
- **Archive and restore chats.** Hide a chat to clear your list, then reopen it later with its
  full context synthesized back — nothing is lost, your workspace just stays tidy. (#1246)

## Improved

- **Web chat, elevated to Mac-grade.** The web Chat and HostedChat gained the polish the Mac
  app has: IME-safe send, a proper Send↔Stop toggle, jump-to-latest, a raised composer,
  history search, drafts, and copy/retry on messages. (#1247)

## Fixed

- **Code and Chat stay put when devices flap.** iOS Code and Chat sessions no longer lose
  their place when a multi-host mesh connection drops and reconnects. (#1248)
- **One Tap sign-in reliability.** The Google One Tap bridge no longer sends an incompatible
  `screen_hint` with GoogleOAuth, fixing a sign-in edge case. (#1245)
