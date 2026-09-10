# 0.96.97

Your Linux and Windows boxes work from the Mac again, and hosted inference stops charging you for models you already pay someone else for. This release closes every bug from the 10 September customer report.

## Your other devices

- A Mac can now actually run sessions on the Linux and Windows machines in your account. Enrolled devices showed as online but every session on them failed as unreachable, because the Mac never set up the connection it needed. It now does, on its own, the moment a device joins your account, and repairs a stale connection within about thirty seconds. (#2045)
- Enrolled Linux and Windows hosts can start sessions again. A cloud check every host runs before a spawn only accepted a person's sign-in, not the host's own credential, so every host answered with an error. (#2045)
- Auto works on an enrolled Linux host. The Mac no longer refuses with "Auto runs on this Mac only", and the run is handed to the host that owns the project. (#2041)
- A device that is offline no longer appears in the start-work picker. You cannot start work on a machine that is not connected, so it is not offered. (#2037)
- Choose repo always does something. When you have no projects yet, it opens a folder, clones from GitHub, or quick-starts a new one instead of doing nothing. (#2037)
- Cloning outside your allowed folders tells you the real reason and where to fix it: add the folder in Settings, Workspaces, or pick one of the roots it lists. It used to blame a protected area that had nothing to do with it. (#2039)
- The same device no longer appears twice in your device list after a re-enrol or a rotated key, and removing a device no longer claims it belongs to another account. (#2038)
- New-device emails open Settings, Devices, instead of landing on a page that said not found. (#2040)

## Hosted inference and billing

- Your weekly hosted-inference allowance counts only what Continuum serves. Usage on your own Claude, Codex or Grok subscriptions is metered for the Usage tab but never counted against the plan you bought from us. Heavy users were locked out of hosted models by their own subscriptions, and no plan or prepaid credit could clear it. (#2045)
- Overage settles the same way. Prepaid credit is no longer drawn down against usage that costs Continuum nothing. (#2045)
- Gemini 3.8 Flash is served through Vertex AI as an official API rung, with the pooled rail kept as fallback. Same model, same price, no change for you. (#2043)

## Mac

- Switching tabs is under 100 ms again on large workspaces. (#2042)
- A crash when a project folder changed on disk while the sidebar was watching it is fixed. (#2042)
- Usage history no longer forgets older records under heavy use. (#2042)
