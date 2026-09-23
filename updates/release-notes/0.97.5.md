# 0.97.5

Muse Code works again right after you sign in, and Continuum stops asking for your keychain password over and over.

## Muse Code

- Signing in to Meta now shows Muse Code as Ready, and new Muse sessions start. Continuum was looking for the `muse` command in the wrong places when opened from the Dock, so it reported you as signed out even after a successful sign-in.
- The "Continuum wants to access key ai.meta.dev.credentials" password prompt no longer repeats. Continuum asks at most once per Meta account; choose Always Allow and it never appears again. Muse keeps working even if you choose Deny.
