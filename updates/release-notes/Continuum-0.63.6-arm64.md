# Continuum 0.63.6

Your phone now stays current on its own. The Mac publishes your usage to Continuum Cloud every minute, so the iPhone Usage tab paints instantly on open and keeps showing your spend even when the Mac is asleep or unreachable. On top of that, your other computers become workers — a Windows or Linux desktop signed into the same account can take on sessions offloaded from your Mac, with its workspaces mirrored so the work lands in the right place. Plus a cross-platform Download hub, a full iOS widget lineup, Chat surfacing every orchestrated sub-agent, and a batch of Mac and chat reliability fixes.

## Features

- **Your iPhone Usage tab stays live on its own.** The Mac now syncs an age-downsampled analytics snapshot to Continuum Cloud every 60 seconds under your account, and the iPhone falls back to it whenever the Mac is unreachable — with a local cache so Usage paints instantly on cold open instead of waiting on the Mac. (#1147)
- **Offload sessions to your own Windows or Linux desktop.** A Continuum desktop app signed into the same account now registers as an offload host, so your Mac can hand sessions to it and get them back — with the desktop's workspaces mirrored through the Go agent so files resolve to the same place on both machines. (#1145)
- **A single place to download every client.** The site gains a multi-platform Download hub that points you at the right Continuum build for Mac, Windows, Linux, iOS, and the CLI. (#1146)
- **A full iOS widget lineup.** New home-screen and Lock Screen widgets mirror the Mac Usage tab, so your spend, limits, and activity are a glance away on your phone. (#1137)
- **A faster Code composer.** The Mac Code composer opens with file-attach available directly, so you can pull a file into the prompt without extra steps. (#1140)
- **Authenticate GitHub in Settings.** GitHub sign-in moved to Settings instead of interrupting you at worktree creation, so setting up a new worktree no longer stops to ask you to log in. (#1135)

## Fixed

- **iPhone analytics no longer wait on the Mac.** The Usage tab stops sitting on "No spend yet" until you open the Mac's Usage tab — the daemon now activates analytics on demand, and the live poll skips re-downloading unchanged data. (#1147)
- **No more double transcripts or worktree freezes on Mac.** Claude no longer writes a duplicate transcript, and creating a worktree no longer freezes while spawning. (#1144)
- **Land back in the app after signing in on the web.** Completing device authentication now opens the signed-in web app directly instead of leaving you on a bare confirmation. (#1142)
- **Every sub-agent shows up in the transcript.** Orchestrated runs now surface each sub-agent's activity in both the Mac and web transcripts, so nothing runs invisibly. (#1141)
- **Follow-ups to Claude queue safely.** Sending another message while Claude is mid-turn now queues it reliably instead of racing the in-flight response. (#1138)
- **Cleaner "Start new session."** Starting a new session after interrupting a tool call no longer resends the original prompt. (#1136)
- **Wide metric tables render compactly.** Chat now lays out wide metric tables without blowing out the message width. (#1139)

## Under the hood

- Windows and Linux desktop installers now build and publish through a dedicated CI workflow, with a Windows Go-build and `.deb` packaging fixes so the cross-platform binaries link and install correctly.
