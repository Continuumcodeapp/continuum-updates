# Continuum 0.74.0

Your iPhone's Action Button can now start Continuum Voice without opening the
app, the Code list stops fighting you when you swipe to archive, and the docs
site is back.

## What's new

- **Toggle Continuum Voice from the Action Button.** Assign Continuum to your
  iPhone's Action Button (or a Control) and one press starts dictation, another
  finishes it — without opening the app first. It works from a cold start, not
  just when Continuum is already running. (#1388)
- **Swipe-to-archive stays open long enough to tap.** Swiping a session in the
  Code list used to snap shut before you could hit **Archive**. The row now
  rests open, swiping a second row closes the first, and tapping the card closes
  the row instead of opening the session. (#1387)
- **The Codex 5-hour bar stops appearing when there is no 5-hour window.** On a
  weekly-only Codex plan, iOS Usage showed a phantom session rail stuck at a
  dead value. Weekly now takes the main gauge and the empty 5-hour rail is gone,
  matching what the Mac already showed. (#1390)
- **continuumcode.ai/docs loads again.** The docs site was rendering an
  "Error loading page" shell for everyone, including search engines. It renders
  properly now, and the docs pages are finally being indexed under our own
  domain instead of the hosting provider's. (#1391)

## Under the hood

- Session diff counts announce their refresh explicitly instead of relying on an
  unrelated event to carry them, and the per-session event filter no longer
  depends on an accident of the visibility check to deliver product-wide
  refreshes. (#1389)
- `hasSession` is now carried end-to-end on the shared usage row, so Mac, iOS,
  web, and the desktop apps all agree on whether a provider actually has a
  rolling session window. (#1390)
- The docs proxy keeps React's streaming payloads byte-stable while still
  rewriting SEO metadata, and stamps a canonical URL and indexing headers on
  every docs response. (#1391)
