# Continuum 0.96.22

Device sync fixes for phones and desktops.

- **iPhone connects to your computers again.** Adding an Android device to your account made iPhone builds treat that phone as a computer to connect to, so they stopped reaching your Mac. iPhone now understands Android devices, never auto-connects to another phone, and a single bad device row can no longer blank the whole device list. (#1714)
- **Android connects to your Mac.** The Android app's relay encryption now runs on Android's JavaScript engine (it previously required WebAssembly), and a secure random source is installed before any encryption runs. (#1712)
- **Mac account sync stops failing every minute.** Custom providers are uploaded in the right order, tokens are only rotated when they actually changed, and revoked or rejected accounts stop retrying, so accounts delivered from other devices now install on the Mac. (#1710)
- **Windows and Linux desktops enrol into your account automatically** and heal a missing enrollment on their own, so accounts you connect there show up everywhere. (#1713)
- **First-run consent screen** now says where your content really goes (the computer you connected the provider on, or Continuum Cloud when it's offline) and lists every supported provider. (#1708)
- **Cloud:** Grok can be connected with a device code from any device; custom providers install on Cloud runners from the delivered material. (#1705, #1709)
