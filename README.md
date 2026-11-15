# The Twenty-Fourth Bell — v0.3 Four-Player Foundation (GitHub Pages)

A four-player, server-backed version of Paco's Day 1. Sign in with an email magic link, claim a character seat, and your progress saves to the party so it follows you across devices.

## What's new in v0.3

- **Sign-in:** Email magic link (passwordless). Invite-only: new sign-ups are disabled in Supabase; only invited family members can sign in.
- **Character select:** Six classes (Rogue, Wizard, Fighter, Cleric, Ranger, Bard). Four seats. Paco the Rogue keeps the real Day 1 story; the other classes are clearly labeled placeholders with a small temporary discovery to try.
- **Server-backed progress:** Your Day 1 choice and dice outcome are saved in Supabase (player_state), not just this browser. Refreshing or switching devices keeps your result. Paco's existing Day 1 from the prototype is migrated to the server on first sign-in.
- **Server-side dice:** Tapping Roll calls a database function that generates the d20 on the server and saves it atomically, so a refresh cannot reroll. The 1.55-second animation and the landing sound cue are unchanged.
- **Share discovery:** After learning a clue, Paco can tap "Share discovery with party" to publish only that clue to the shared party journal. Private journal entries (including the Renn secret) are never shared.
- **Party screen:** Shows the real claimed seats and the shared journal entries, live from the server.
- **Backend:** Supabase (free tier) project "the-twenty-fourth-bell", region us-west-1. Tables: parties, players, player_state, shared_journal, party_flags. Row Level Security keeps each player's private state visible only to them. The dice function is `roll_day1_check`.

## Audio v0.2 (unchanged in v0.3)

- Synchronized, original synthesized dice-tumble sound (~1.55 seconds).
- Success / complication chimes after the die settles.
- Door-opening audio when entering Day 1 from the calendar.
- Sound-effects enable/disable toggle. Preference persists across reloads.
- Music cues automatically when Day 1 is opened (iOS Safari blocks true autoplay before a tap, so the door tap is the first gesture that starts it). Music on/off toggle persists across reloads; turning it off keeps music silent.
- Day 1 ambient score, “A Town Without a Bell” (Suno, ~2:55, stereo), at `audio/day01_theme.mp3`. The synthesized demo loop remains at `audio/day01_theme_demo.mp3` as a fallback and is no longer referenced by the page.
- Dice generation, outcomes and save system intentionally unchanged. No backend, multiplayer, analytics or permissions.

## Deploy with Donaar

1. Treat this as a patch against the previous version of `The Twenty-Fourth Bell`, not as proof of the exact contents of the live GitHub repository. Compare first to avoid overwriting newer fixes.
2. Replace the site's root `index.html` after reviewing differences, and add the `audio/` directory. Keep `.nojekyll` as already present.
3. Commit, push to `main`, wait for the GitHub Pages deployment, then open the URL on an actual iPhone.
4. Test that tapping Roll plays a 1.55-second dice rattle and the appropriate landing cue, and that no reroll is possible after refresh.
5. Test the Effects and Music controls, browser refresh, page backgrounding, and audio on/off in Safari. Check that background music pauses when the tab is hidden and does not automatically play on loading.

## Day 1 background score

The Day 1 score is the Suno track “A Town Without a Bell” at `audio/day01_theme.mp3` (~2:55, stereo). The page references it from the `<audio>` element and labels it 'Day 1 · The Favor'. To swap in a different track, replace that file and keep the same filename; the page needs no code change. Keep the .mp3 under this same site's origin for reliable mobile playback. The synthesized demo loop is still in the repo at `audio/day01_theme_demo.mp3` as a fallback.

## Sound choices

Effect assets are original synthetic audio generated specifically for this prototype; no third-party sound libraries, credits, or license obligations. Effects never influence the dice result.

## Future music design

Build around one recurring motif, changing harmonic/color instrumentation every day. Avoid the full 24-track production investment until Day 1's music and audio mix are tested on all four family phones. Add user-controlled volume and per-day soundtrack selection when we expand the story beyond Day 1.
