# Continuum 0.58.1

A focused follow-up to 0.58.0.

## Fixed

- **Cursor models are back in the picker.** The model picker's Cursor tab showed only "Cursor default / Auto" — the live cursor-agent model list never loaded. When you're signed in to Cursor, the picker (Mac and iOS) now shows your account's real model list; signed-out Macs keep the safe behavior that never touches Cursor's Keychain on startup. (#971)

Ships build 295 for Mac (signed Sparkle feed).
