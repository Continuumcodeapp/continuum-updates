# Continuum 0.73.0

Ten fixes aimed squarely at the iPhone: the Code tab now shows only real code
sessions, the transcript and timer agree with the Mac, and starting a session
feels like starting a conversation. Plus your disk stops quietly filling up.

## What's new

- **Starting a session on your phone is a conversation now, not a wait.** Tapping
  send used to park you on a blank screen for several seconds and then drop you
  back on the Code list, sometimes with an empty transcript. You now see your own
  message immediately, a four-step setup trail while the workspace is prepared,
  and you land directly in the live transcript. (#1380)
- **Chat transcripts stopped leaking into Code.** For the first 15–20 seconds
  after opening the app, Chat conversations were grouped into the Code tab — with
  their activity animations running. Code now shows only real, repository-backed
  code sessions from the first frame. (#1377)
- **Your phone shows the same transcript and timer as the Mac.** When an agent
  rolled over to a new session file, the phone could keep rendering an older
  reply and count elapsed time from the wrong prompt. Both now follow the Mac,
  and stale pages are replaced atomically instead of lingering. (#1379)
- **Running sessions look running on iPhone.** A session that was actively
  streaming could appear idle on the phone while the Mac showed it working. Both
  hosts now publish the real per-turn activity, so the data-stream animation
  matches everywhere. (#1381)
- **Create PR no longer appears mid-turn.** The overflow menu still offered
  *Create PR* while the agent was working — and on hosts that can't open PRs at
  all. It now uses the exact same end-of-turn rule as the main button. (#1378)
- **Continuum's own setup text stays out of your transcript.** The internal
  repository briefing Continuum sends with your first prompt was being rendered
  as if you had typed it. It's hidden now, on new and existing conversations
  alike, and a failed turn no longer leaves a duplicate copy of your message
  behind. (#1384)
- **Screenshot names survive in attachment pills.** A file like
  `Screenshot 2026-08-01 at 9.08.48 AM.png` was cut at `.48`, leaving a stray
  `AM.png` in the message text. The whole filename stays in the pill. (#1383)
- **The Settings sidebar scrolls.** In a short window the lower settings groups
  were simply unreachable on Mac, Windows, Linux, and the web. The list now
  scrolls on its own. (#1382)
- **Archived worktrees stop eating your disk.** Archiving a session was supposed
  to reclaim its worktree and silently never did — 67 stale worktrees, several
  gigabytes, on one machine. Reclaim works now, a background sweeper cleans up
  what leaked before, and build output is deleted outright instead of piling up
  in a Trash nobody empties. (#1385)
- **Hosted sessions attach on the first try.** A hosted session could report
  success before it was actually connected to its provider, leaving a session
  that could never be used or retried. It now attaches exactly once, and repeat
  requests replay only verified state. (#1386)

## Under the hood

- Transcript cloud sync only replaces a generation when both the source counter
  regresses and the transcript actually shrinks, with restart-safe publisher
  state on Mac and the Go host, and generation-atomic page replacement. (#1379)
- Worktree reclaim is linearized against racing spawns and unarchives, compares
  paths by filesystem identity rather than spelling, and cross-checks the on-disk
  ownership marker against the session record before deleting anything. (#1385)
- Hosted session creation is single-flight per stable ID and rejects mismatched
  repo, agent, mode, or lifecycle on replay; private hosted capacity now runs over
  HTTPS with an operator-owned CA, and deploys fail early if that CA is missing or
  near expiry. (#1386)
- The Code gate, the Create-PR gate, and the attachment parser each moved into a
  single shared implementation, so Mac and iOS can no longer drift apart on what
  counts as a code session, when a PR can be opened, or where a filename ends.
  (#1377, #1378, #1383)
