# Continuum 0.83.0

## What's new

- **Continuum can drive your browser now.** Install the Continuum Chrome extension and any session can read and act in your real, logged-in browser — navigate, click, type, check the console — with a permission model built for humans: one card to let a session drive a site, and separate, explicit consent for running JavaScript, uploading a file, or listing your other tabs. Grants are per-site and can be "just this session" or remembered, and everything is revocable in Settings. A panic control releases the browser instantly. (#1459, #1477)
- **Computer use: watch it work, step by step.** Sessions that drive the browser or your desktop now render each action as a first-class step in the transcript — with screenshots — on Mac, iPhone, and web, and a live view streams what's happening as it happens. The desktop-control ring shows a visible indicator whenever a session is driving your Mac, refuses sensitive apps (password managers, Apple's Passwords app), and stops on a global ⌥⌘. panic hotkey. (#1480, #1483)
- **Long sessions stay fast and light.** Analytics moved to a bounded, per-file store with a strict memory budget, live motion moved off the render loop, and the transcript now windows very long conversations — so a Continuum you leave running all day no longer creeps up in memory or gets sluggish to scroll. (#1460)
- **Hit your session limit? The recovery buttons show up now.** Claude's newer "you've hit your session limit" wording is recognized, so the "continue with your other account" recovery actually appears instead of the session dead-ending. (#1476)
- **Theme selector on iPhone and the Expo app**, and every path that could force the app to light mode against your choice is gone. (#1470)
- **OpenCode shows its real quota rails** — your actual 5-hour, weekly, and monthly limits — on iPhone, web, and desktop, instead of dead spend tiles. (#1472)

## Fixes and under-the-hood

- The Code tab no longer crash-loops when two repos share a name. (#1474)
- The live data stream is back on working Code rows on iPhone, and stray mobile session status dots are gone. (#1473, #1471)
- Transcript text selection and copy work correctly again, and raw Codex file citations render properly instead of leaking their internals. (#1467, #1461)
- Your device and repo picks in New Session are now sticky — they survive a host going to sleep, a Wi-Fi switch, or a relaunch, instead of silently resetting to whatever was online first. (#1464)
- Device mesh is on by default for signed-in users, with a hardened lifecycle so a transient keychain hiccup can't tear it down. (#1463, #1469)
- Active PR sessions stay in Active instead of falsely reading as idle. (#1462)
- Settings connectors on iPhone collapse behind a Browse control so the list stays manageable. (#1475)
- Sidebar active-session lifecycle is locked down by tests to prevent regressions. (#1468)
