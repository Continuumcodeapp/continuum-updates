# Continuum 0.65.2

Continuum Plus arrives — a $25/month tier with hosted inference built in — alongside four
free hosted models in the picker, a rebuilt first-run experience, and a round of Chat, Code,
and billing fixes across iOS and Mac.

## New

- **Continuum Plus.** A new $25/month plan that includes hosted inference with a $25/week
  usage cap, so you can run models through Continuum without bringing your own key. The native
  app shows a live weekly usage gauge, and the cloud dashboard surfaces the tier label and
  remaining budget. (#1230, #1231, #1232)
- **Four free hosted models.** The Continuum picker now offers Nemotron 3 Ultra, Nemotron 3
  Super, Gemma 4 31B, and North Mini Code at no cost — pick one and start coding without a
  paid provider. The hosted catalog was also trimmed to only models that actually serve, so
  you never select one that can't run. (#1238, #1235)
- **A rebuilt first run.** Onboarding is now a guided, per-provider setup with cleaner empty
  states and a working Quick Start — no more confusing web-org step. New installs get to a
  working session faster. (#1228)

## Fixed

- **Model selection that tells you the truth.** Choosing Continuum as your provider now
  surfaces gateway errors instead of failing silently, only offers models the live catalog can
  actually serve, and counts Continuum correctly in broadcast. (#1227)
- **No more hidden voice-shortcut capture on Mac.** The voice shortcut no longer grabs
  keystrokes when it shouldn't. (#1226)
- **Cleaner model menu on Mac.** Settings no longer repeats the "Continuum" brand prefix on
  every hosted model name. (#1225)
- **Fable sends reliably.** Recovered a first-send idempotency conflict that could stall the
  very first message to a Fable model. (#1234)
- **Accurate document tabs on Mac.** Tool output with a bare filename no longer fabricates a
  bogus document-tab path. (#1240)
- **iOS Chat & Code polish.** The New Chat button keeps its intrinsic size, Code session-card
  diff stats are vertically centered, and the header CTAs are more compact with the Code
  "Add a device" promo removed. (#1222, #1223, #1224)
- **Correct Fable pricing.** claude-fable-5 is now billed at its list rate ($10/$50 per Mtok)
  instead of falling back to a Sonnet-class price. (#1233)
- **Admin invites, fixed.** Creating an invite no longer throws a silent 520, "Pro" is renamed
  to "Continuum App," the email field is sized correctly, and invites now default to a 3-month
  Continuum App code. (#1229, #1239)
