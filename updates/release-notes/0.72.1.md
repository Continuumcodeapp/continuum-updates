# Continuum 0.72.1

Nine fixes in one pass, all aimed at the same theme: every client — Mac,
iPhone, web, Windows/Linux — should agree about what's happening and stay
usable while it happens.

## What's new

- **Every client now agrees who's working.** The real per-turn activity signal
  is published on the wire, so sessions animate (and stop animating) together
  on the Mac, iPhone, and web instead of six spinners on one screen and one on
  another. Diff counters also land faster on busy worktrees. (#1374)
- **PR badges stop disagreeing across devices.** "We haven't checked yet" is no
  longer rendered as "no PR": branch/PR state is remembered between checks,
  externally-merged PRs are detected, and a host with a broken `gh` can no
  longer wipe good badges for everyone. (#1372)
- **Starting a session from your iPhone no longer fails on slow repos.** Every
  hop between the phone and your Mac now allows the same per-endpoint time
  budget, so a first run with a long setup script finishes instead of dying at
  a 10-second relay ceiling — and when something does go wrong, you see the
  real reason instead of "Could not start the session." (#1371)
- **The copy button waits for the turn to actually end.** On iPhone, the
  end-of-turn footer (copy, duration, edited files) no longer appears while the
  agent is still working — and on web it now reliably appears once the turn
  settles. (#1373)
- **Create PR shows up exactly when it should.** On iPhone it no longer
  reappears mid-turn right after you send; on Android/Expo it now appears at
  all (it was permanently hidden). (#1370)
- **The Code header fits on a phone again.** After creating a PR, the title
  keeps its full width, `#1368` and `Merge` no longer wrap mid-word, and the PR
  number always renders without locale separators. (#1375)
- **The session list scrolls from anywhere.** A full Code tab no longer traps
  vertical swipes on the cards — scroll starts anywhere, and only a deliberate
  left swipe reveals Archive. (#1368)
- **The composer's model and effort pills stopped colliding.** They're now one
  split capsule with both halves tappable — on iOS and Expo. (#1369)
- **Your first message no longer hides under the reply.** Repos with a dot or
  other punctuation in their path (like `glide.co`) resolved to a transcript
  directory Claude never writes, pinning your prompt below the streamed answer.
  Continuum now names transcript directories exactly the way Claude Code does.
  (#1376)

## Under the hood

- Self-hosted CI runners repaired: container jobs no longer leave root-owned
  files that break every following checkout.
- A date-sensitive backend test fixture was made relative so the cloud deploy
  gate can't trip on the calendar.
