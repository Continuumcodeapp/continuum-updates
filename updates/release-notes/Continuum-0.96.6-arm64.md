# Continuum 0.96.6

## Features
- Connect GitHub without leaving the app, on Mac and iPhone: sign-in, org pick, and repository selection finish in one in-app pass instead of bouncing through Safari and parking on a "One more step" page an app-only user could never complete (#1638)

## Fixes
- Long-running provider turns are never ended by a clock anymore. A turn completes only on the provider's own signal, your Stop, or confirmed process loss after recovery, so multi-hour work stays live on Mac and Linux/Windows hosts alike, and elapsed time is diagnostics only (#1635)
- A cancel the agent refuses no longer paints the run as dead while it keeps working, and a session whose provider goes quiet mid-retry now resolves cleanly on the live stream instead of spinning forever (#1635)
- Switching Continuum members now fully signs the previous member out of the in-app GitHub browser, including legacy org sign-ins, interrupted sign-outs, and unreadable session state (#1638)
- The in-app GitHub browser is stricter about what leaves the app: only a page you can see may hand off to the system browser or Mail, and a failed authorization callback no longer leaves Settings stuck on "Waiting for GitHub" (#1638)

## Docs and site
- New Cursor vs VS Code comparison, 2026-dated Cursor comparison titles, an upgraded agentic coding landing page, and corrected Cursor pricing across the guide corpus (#1636, #1637)
- Three high-traffic guides now close on Get Plus with hosted Plus pricing (#1639)
