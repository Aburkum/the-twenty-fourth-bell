# The Twenty-Fourth Bell — Audio v0.2 (GitHub Pages)

A fully self-contained static prototype of Paco’s Day 1 with added sound effects and music controls.

## What's new

- Synchronized, original synthesized dice-tumble sound (~1.55 seconds).
- Success / complication chimes after the die settles.
- Door-opening audio when entering Day 1 from the calendar.
- Sound-effects enable/disable toggle. Preference persists across reloads.
- Explicit Play/Pause Music toggle that works with phone browser policies.
- Original, synthesized **demo** Day 1 ambient loop (40s). **This is NOT a Suno track** and should be replaced with a Suno instrumental as soon as selected.
- Dice generation, outcomes and save system intentionally unchanged. No backend, multiplayer, analytics or permissions.

## Deploy with Donaar

1. Treat this as a patch against the previous version of `The Twenty-Fourth Bell`, not as proof of the exact contents of the live GitHub repository. Compare first to avoid overwriting newer fixes.
2. Replace the site's root `index.html` after reviewing differences, and add the `audio/` directory. Keep `.nojekyll` as already present.
3. Commit, push to `main`, wait for the GitHub Pages deployment, then open the URL on an actual iPhone.
4. Test that tapping Roll plays a 1.55-second dice rattle and the appropriate landing cue, and that no reroll is possible after refresh.
5. Test the Effects and Music controls, browser refresh, page backgrounding, and audio on/off in Safari. Check that background music pauses when the tab is hidden and does not automatically play on loading.

## Replacing the temporary background score

Download a selected Suno instrumental MP3 and put it at `audio/day01_theme.mp3`. Edit `index.html`: change the audio `src` from `audio/day01_theme_demo.mp3` to `audio/day01_theme.mp3` and the `audioStatus` labels from 'Demo theme' to 'Day 1 · The Favor'. Keep the .mp3 under this same site's origin for reliable mobile playback.

## Sound choices

Effect assets are original synthetic audio generated specifically for this prototype; no third-party sound libraries, credits, or license obligations. Effects never influence the dice result.

## Future music design

Build around one recurring motif, changing harmonic/color instrumentation every day. Avoid the full 24-track production investment until Day 1's music and audio mix are tested on all four family phones. Add user-controlled volume and per-day soundtrack selection when we expand the story beyond Day 1.
