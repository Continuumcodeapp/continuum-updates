# Continuum 0.57.7

Security hardening ahead of an external pentest, a smarter model picker, a batch of Mac polish, and a refreshed website.

## New

- **The model picker remembers your Favourites.** When you've starred models, the picker now opens straight to the Favourites tab instead of the full list. (#786)
- **A polished, on-brand Mac installer.** The downloaded DMG now opens to a styled installer window that matches the app. (#791)

## Fixed

- **Cleaner workspace state.** Archived and deleted sessions are pruned from a workspace's active list, so stale entries no longer linger in the sidebar. (#788)
- **Composer + repo-header polish.** The new-session "+" matches its sibling icon buttons, and the composer's create action carries the right state. (#787, #790)

## Under the hood

- **Pre-pentest security hardening.** A four-wave adversarial security audit (Claude + Codex, ~150 findings triaged) closed P0/P1/P2 issues across the Mac/iOS/Watch apps, the Continuum Cloud backend, and the Linux agent — SSRF, symlink-follow, injection, trust-gate, and denial-of-service fixes — ahead of an external penetration test. No user-facing behavior changes. (#793–#796)
- **Refreshed website + one-click Mac download.** continuumcode.ai gets a cleaner landing page, docs served at /docs, web analytics, and a direct "Download for Mac" button. (#781, #784, #785, #789, #792)

Ships build 278 for Mac (signed Sparkle feed).
