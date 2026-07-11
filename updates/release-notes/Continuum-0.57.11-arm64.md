# Continuum 0.57.11

Mobile companion polish: the iPhone Chat and Code tabs work better against your paired Mac - single-provider chats now open as a live Solo conversation, the Code tab lists your repos even before any sessions exist, and disabled providers no longer flash into the model pickers.

## Improved

- **iPhone Code tab shows your repos right away.** The Code tab now lists every managed repo with a tappable "New session" row even when none of them has a session yet - tap one to open the composer already pointed at that repo. The Mac daemon refreshes its repo list on request so a freshly-launched Mac populates the list immediately. (#816)

## Fixed

- **Single-provider chats work on iPhone.** Picking exactly one provider in iPhone Chat now opens a live Solo conversation (it creates the session and streams the reply) instead of being rejected with "pick at least two providers to broadcast." Follow-ups continue in the same thread. (#817)
- **Disabled providers stop flashing into the iPhone model pickers.** Providers you've turned off (e.g. Antigravity) no longer appear for a moment in the mobile model/provider pickers before your Mac's catalog loads - the picker now respects your enabled set from the start. (#815)
- **iPhone broadcasts carry full provider metadata.** A one-tap broadcast from iPhone now sends each provider's full slot info (vendor identity, billing provider, and default effort) instead of a stripped-down provider/model only, and surfaces the Mac's actual error if a broadcast can't start. (#814)

Ships build 282 for Mac (signed Sparkle feed) and iPhone/Watch (TestFlight).
