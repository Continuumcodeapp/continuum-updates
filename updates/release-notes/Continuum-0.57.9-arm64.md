# Continuum 0.57.9

A big batch of ways to run and connect agents: SSH/Termius hosts, serverless burst capacity, subscription sign-in, GitHub/Linear integration, and a Mac-parity iPhone composer.

## New

- **Connect any SSH or Termius host as an execution host.** Continuum discovers your SSH config / Termius hosts, installs its agent over SSH, and pairs the device onto the relay - so you can run agents on a remote Mac or Linux box without manual setup. SSH is used only for bootstrap; sessions route over the relay. (#802)
- **One-tap subscription sign-in for Claude & Codex.** Provider setup now defaults to subscription OAuth - Claude via setup-token, Codex via device auth - and rejects API-key-only auth so you can't accidentally bill the wrong account. Your credentials seed automatically to your connected mesh devices. (#801)
- **GitHub and Linear, inside Continuum.** Paste a GitHub or Linear issue URL as your first prompt and Continuum pulls the issue in as context, then links the generated branch and PR back to the source issue. Line comments in the diff/PR pane post to GitHub as review comments, with replies threaded inline. (#803)
- **Cloud Burst - serverless execution hosts.** Add short-lived Vercel or Cloudflare sandboxes as on-demand execution hosts, with bring-your-own / managed quota caps and automatic idle and hard-cap stops. (#800)
- **iPhone composer reaches Mac parity, plus one-handed review.** The iOS session composer gains inline model/effort, Plan/Code and Local/Worktree controls, file + photo attachments, slash-command and @-mention palettes, prompt history, and send/stop. A new one-handed review mode in the Diff tab lets you Comment, Approve, or Send Back right on the changed-file list and line-level diff. (#804)

## Under the hood

- Hardened the new SSH and credential-seeding paths (host-validated issue-URL parsing with no arbitrary fetches, relay tokens that never leave your Mac, fail-closed credential push) and fixed a cross-platform build issue so SSH host discovery compiles on iOS.

Ships build 280 for Mac (signed Sparkle feed).
