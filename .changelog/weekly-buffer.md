<!--
This file is managed by the /changelog Claude Code skill.
Do not hand-edit. See .changelog/README.md for the entry format.
Buffer is empty at start of each week.
-->

<!-- entry:2026-04-22 tag:feature -->
## Ship your agent on your own domain

Attach a subdomain or apex to any hosted agent, then set a per-agent page title, description, OG preview, and favicon so shared links look like yours — not ours.

![A cream editorial card titled "Bring your own domain" floating on a warm off-white canvas with faint concentric rings radiating behind — the card holds a globe icon pill at the top, the headline, a short subtitle, a labeled "Your domain" input with an https:// prefix and the placeholder chat.yourcompany.com, and a dark "Attach domain" button at the bottom](https://docs.mascot.bot/images/changelog/ship-your-agent-on-your-own-domain.png)

- Custom domain attach via the Vercel Domains API — paste the hostname, copy one DNS record, we auto-poll and verify the moment propagation lands.
- Per-agent SEO: `<title>`, description, OG image, favicon — with a live Slack / Twitter / browser-tab preview right next to the inputs.
- Works for both standalone and widget-hosted agents, subdomain or apex.

[Read more →](https://docs.mascot.bot/changelog#ship-your-agent-on-your-own-domain)

<!-- /entry -->

<!-- entry:2026-04-22 tag:feature -->
## A lipsync playground against real voice streams

The new `/lipsync-test` tool lets you upload any Rive mascot, wire a Gemini Live session or plug in your own ElevenLabs agent, and dial every SDK knob — critical-viseme holds, min intervals, transition speeds — while the mascot responds in real time.

![The /lipsync-test page rendered as a tilted editorial product shot on a warm cream canvas with a subtle dot grid — a friendly cartoon blue cat mascot sits centered on a sandy beach under a blue sky, flanked on the right by a vertical stack of cream settings panels for Rive File, Display Settings, Voice Provider (Gemini Live / ElevenLabs), Voice, Lip Sync Model, and Lip Sync Settings](https://docs.mascot.bot/images/changelog/lipsync-test.png)

- Switch providers on the fly: **Gemini Live** (preset) or paste your own ElevenLabs API key + agent ID — credentials stay in your browser.
- Every `NaturalLipSyncConfig` field is a live slider; changes apply mid-call without resetting playback.
- Chip selector for the critical viseme set (r, l, f/v, p/b/m by default; toggle any of 21 to taste).
- Replay captured responses against tweaked settings to A/B feel without re-speaking.
- Upload any `.riv` file to test your own mascot; HD-zoom + pan the canvas to inspect mouth shapes.

[Read more →](https://docs.mascot.bot/changelog#a-lipsync-playground-against-real-voice-streams)

<!-- /entry -->

<!-- entry:2026-04-22 tag:feature -->
## Tune your mascot's lipsync mid-call, without reset

Mascotbot SDK `0.2.0` adds critical-viseme holds, a configurable critical set, and a live-update pipeline — every phoneme knob now takes effect on the next viseme chunk, mid-call, without breaking the stream.

![A two-column release-card composition on a dark canvas — left, a real cream-colored Lip Sync Settings panel with the Natural Lip Sync toggle on, the Natural Lip Sync preset active, and five orange-tracked sliders for Min Viseme Interval, Merge Window, Key Viseme Preference, Similarity Threshold, and Critical Viseme Min Duration; right, a huge metallic-white wordmark reading SDK 0.2.0 on two lines](https://docs.mascot.bot/images/changelog/sdk-0-2-0.png)

- `criticalVisemeMinDuration` holds u/o/r/l/f/v/p/b/m phonemes long enough to register, dropping any non-critical viseme that would interrupt the hold window.
- `criticalVisemeIds` exposes the critical set — drop vowels, add sibilants, whatever fits your character. Exports `DEFAULT_CRITICAL_VISEME_IDS` for consumers to derive custom lists.
- `desktopTransitionSpeed` / `mobileTransitionSpeed` replace the misleadingly-named `*Duration` fields (old names kept as deprecated aliases). Default bumped from `11` → `22` for snappier blends.
- Config edits now flow through the active `MascotPlayback` in place; slider tweaks and preset changes don't tear down the stream.
- Perf tuning validated on `/lipsync-test`: memoized side panels, ref-based viewport pan/zoom, identity short-circuit on per-chunk config sync, NoiseOverlay visibility gate.

[Read more →](https://docs.mascot.bot/changelog#tune-your-mascots-lipsync-mid-call-without-reset)

<!-- /entry -->
