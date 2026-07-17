# Continuum 0.64.0

Your chat history now lives in your account, not on one machine. The Mac publishes every session's transcript to Continuum Cloud as you work, and your iPhone follows along in real time over a live push stream — open a past session on the phone and it loads instantly, even when the Mac is asleep, shut down, or on another network. Transcripts are encrypted at rest under per-member keys, Windows and Linux agents publish the same way, and the phone↔Mac link no longer drops every 15 minutes.

## Features

- **Transcripts sync across devices in real time.** The Mac publishes each active session's chat transcript to Continuum Cloud within seconds, and a member-scoped push stream tells your other devices the moment something changes — no polling, no "pull to refresh." (#1149, #1157)
- **Past sessions open with the Mac off.** The iPhone reads transcripts straight from your cloud account (a rolling 30-day window per session), so history is available anywhere you're signed in — the Mac being unreachable no longer means a blank screen. (#1157)
- **Session lists and transcripts paint instantly on iPhone.** Cold open draws from a local cache first, then refreshes live — no more staring at black while a transcript loads. (#1157)
- **Cowork runs reach your phone.** When a cowork task needs your OK, the phone raises a notification even if Continuum is in the background. (#1157)
- **Encrypted at rest.** Cloud transcripts are sealed with per-member AES-256-GCM keys; removing a member crypto-shreds their content. (#1157)
- **Windows and Linux publish too.** The Go agent gains full transcript-publishing parity with the Mac at the same cadence, on by default. (#1157)

## Fixed

- **The phone no longer loses the Mac every 15 minutes.** The relay's idle eviction now counts delivered keepalives as activity, so long-lived host connections stay up instead of churning through reconnects. (#1149)
- **Cloud sync starts on every launch.** The usage mirror and transcript publisher now start from the menu-bar launch path, so a Mac that never opens the main window still publishes. (#1149)
- **continuumcode.ai serves the real site again.** The box deploy now assembles the marketing site and the `/app/` dashboard instead of a placeholder stub. (#1157)

## Under the hood

- Windows code-signing scaffold (inert until certificates are provisioned) and non-fatal FFF staging on Windows build hosts.
- Migration-runner hardening and box deploy web-asset assembly.
