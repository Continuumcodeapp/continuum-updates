# Continuum 0.78.0

## What's new

- **Open another tab in the same working copy.** The workspace tab strip gains a "+" that spawns a second agent in the same worktree — two agents, one checkout, no second clone. Closing a tab now genuinely ends that tab's agent instead of hiding a session that keeps running (and billing) in the background. Ships on Mac, iPhone, web, Windows, and Linux, against both the Mac and Linux hosts. (#1417)
- **Your device and repo picks finally stick.** Starting a session from the phone kept landing on the wrong Mac, and the repo chip could reset itself mid-typing whenever a host blipped. An explicit pick is now remembered on every client and survives disconnects, list refreshes, and relaunches — it's released only when the device or repo actually leaves your account. (#1418)
- **The Action Button reliably delivers dictation.** Pressing the iPhone Action Button with the Continuum keyboard up now records, shows a live waveform while you speak (even in silence), and lands the transcript in the field — with a clipboard fallback so a slow keyboard never loses your words. (#1415)

## Fixes and under-the-hood

- **Hosted sessions start reliably on the Mac.** The app now finds Homebrew's keg-only Node for CLI shims, keeps a Continuum-hosted model selection on its own billing rail instead of silently falling back to your Claude subscription, resolves worktree collisions at create time, and surfaces OpenCode's permission prompts on the standard approval card instead of hanging on a silent "Running". Background credential reads were also coalesced, ending the repeated Keychain/file-access prompt storms. (#1408)
- **Stop means stop for OpenCode.** Stopping an OpenCode session now uses the provider's native abort, every client shows the same running/stopped state from one provider-owned signal, and a runtime guard caps runaway turns on wall-clock time and memory — without a host config being able to loosen the safety posture. (#1411)
- The hosted gateway accepts OpenCode's prompt-cache markers on historical tool calls instead of failing the session, while still rejecting unknown extensions. (#1416)
