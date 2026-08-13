# Continuum 0.88.0

## Security
- OAuth connector and GitHub callbacks now prove the completing browser belongs to the member who started the flow — a link opened by anyone else parks the result behind an explicit signed-in confirmation instead of attaching credentials to the wrong account (#1536)
- Approving a plan is now bound to the exact plan revision that was reviewed, and PR approve/merge to the exact reviewed head — a mid-review change can no longer ride an old approval (#1536)
- The connectors sidecar no longer inherits the host's provider secrets, remote hosts refuse wire-supplied setup scripts, and SSH setup output is bounded so one hostile line can't take down the shell (#1536)

## Fixes
- Go-hosted sessions decode on every Apple client again: the Linux/Windows host now emits the same whole-second timestamp contract Swift expects, pinned by tests in both languages (#1537)
- Sessions on Go hosts no longer run your first prompt twice, lose a re-queued prompt, or resurrect terminal panes that died with a previous daemon (#1536)
- Chat history that scrolled out of the live window is recovered on demand, archived sessions keep their transcripts, and content-block order survives the transcript sort (#1536)
- Signing out on iOS actually revokes the account credential, departing team members take their usage history with them, and per-account caches can no longer leak across accounts (#1536)
- The hosted wallet no longer double-counts the same synced history from two enrolled Macs — exact-window costs now agree with what the customer is invoiced (#1536)
- One org's budget timezone can no longer pause every other org's enforcement, and web, desktop, and mobile share the same per-endpoint request budgets (#1536)
- Attachments ship under one cross-host contract: oversized files are refused before the renderer reads them, the file the paperclip picked is the file that uploads, and drafts survive tab switches on iOS (#1536)
- Claude 1M-context models launch correctly on Go hosts, and a model can no longer launch through an alias another model also claims (#1536)

## Under the hood
- Release tooling: a draft release is addressed by its immutable id with retried reads, so a transient GitHub hiccup can no longer abort a publish claiming an asset is "missing" (#1535)
- The AWS BYOC bootstrap installer is published as a content-addressed public release, fetchable by cloud-init with no credential (#1536)
- ~121 verified P1 findings fixed in total across Mac, iOS, web, desktop, the Go agent, and the cloud backend, with 88 new test files (#1536)
