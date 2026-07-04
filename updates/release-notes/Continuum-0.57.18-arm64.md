# Continuum 0.57.18

A hotfix for a launch crash in 0.57.17.

## Fixed

- **Fixed a crash on launch introduced in 0.57.17.** The voice-dictation overlay was pre-warmed too early during app startup, which could abort the app before its window appeared. The pre-warm now runs a moment later, so Continuum launches cleanly. If you updated to 0.57.17 and it wouldn't open, this release fixes it.

Ships build 289 for Mac (signed Sparkle feed). Everything new in 0.57.17 (Z.ai Coding provider, one-tap device setup, the rebuilt continuumcode.ai, OpenCode connect fixes, the reliable Left Option voice trigger, Grok popover, and the sidebar empty state) is included.
