# Continuum 0.57.12

Remote-device setup reliability: you can now minimize a running device install and keep working, Antigravity setup installs the right CLI, and a couple of setup failures that could leave a Linux host half-configured are fixed.

## New

- **Minimize a device setup while it installs.** The "Add Tailscale device" / "Add via SSH" setup sheet now has a Minimize button - the install keeps running in the background as a compact progress dock in Settings → Devices that you can click to re-expand, instead of forcing you to keep the modal open the whole time. The dock clears itself automatically once the device finishes connecting. (#820)

## Fixed

- **Antigravity setup installs the correct CLI.** Setting up Antigravity (the `gemini` provider) now installs Google's official `agy` CLI via its downloader and launches it with the right headless flags, replacing the retired `@google/gemini-cli` path that no longer works. (#819)
- **Remote setup no longer fails on token capture or runtime permissions.** Two setup failures are fixed: the Mac setup terminal no longer aborts with a `read-only variable: status` error (so it correctly shows your command's result and the "click Done" prompt), and the Linux agent's runtime state directory is now writable by the unprivileged service user, so `agent-token` is created and the service comes up instead of silently failing. (#818)

Ships build 283 for Mac (signed Sparkle feed).
