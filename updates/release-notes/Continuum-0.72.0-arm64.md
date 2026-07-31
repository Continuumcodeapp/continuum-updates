# Continuum 0.72.0

Follow-up to 0.71.0's sync work: your Mac stays reachable on its own, and the
phone finally shows the truth about what's running.

## What's new

- **Your Mac heals itself instead of going dark.** After a crash-relaunch or a
  stale enrollment, the Mac could get stuck "offline" forever — no restart or
  re-sign-in brought it back. It now detects the stall, clears the bad
  enrollment, and re-enrolls itself automatically. (#1352)
- **PR controls on your phone finally know what state you're in.** Instead of a
  permanent orange **Create PR** button — which stayed loud after the work was
  done and offered to open a second PR against an already-merged branch — iOS
  and Android now show the same three-state control the Mac has: *Create PR*
  when there isn't one, a colour-coded PR pill when there is, and a *Merge*
  button when checks are green. (#1367)
- **Usage gauges work again on iPhone.** They were pinned at 0% with a
  recurring "Your Mac didn't respond in time" — the phone was asking the wrong
  machine. It now reads usage from a live Mac, and holds the last good numbers
  through a relay blip instead of flickering every five seconds. (#1365, #1366)
- **Live sessions actually look live.** A session running on another device
  showed as finished — no data-stream animation, no "Live on another device".
  Running sessions now report their real status across every client. (#1365,
  #1366)

## Under the hood

- Host-control startup gets a 30-second watchdog and retries on the mirror
  timer, so a single failed enroll can no longer strand a machine. (#1352)
- Sessions resumed after an app restart re-attach their event wiring, so the
  session registry stops publishing a frozen row. (#1366)
- PR-state vocabulary moved into one shared model (Swift + TypeScript) with
  matching tests, so the Mac, iOS, and Expo clients can't drift apart on what a
  merged PR looks like. (#1367)
