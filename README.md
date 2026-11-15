# The Twenty-Fourth Bell — hosted prototype

This repository serves the original v0.1 mobile-friendly, single-file prototype of **The Twenty-Fourth Bell**, a private-family advent RPG concept.

## Deploy with GitHub Pages

1. Put `index.html` at the root of the repository's default `main` branch. It is self-contained: no build step, npm dependencies, server, or database required.
2. In the repository, open **Settings > Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, branch **main**, folder **/(root)**, then **Save**.
4. Wait for GitHub Pages to report successful deployment; use the actual **Visit site** URL rather than guessing.
5. Test on a phone, including a persisted dice result after a page refresh.

GitHub Pages requires a public repository for GitHub Free. A Pages site is publicly viewable even when published from a private repository on a plan that permits it. Do not commit credentials, private family data, hidden future narrative revelations, or API keys.

## Included prototype behavior

- 24-door calendar, with Day 1 of Paco's adventure playable.
- Mobile navigation: Calendar, Story, Journal, Party; a character dossier.
- Four Day 1 narrative choices. Three use player-initiated checks with a d20 animation; one resolves without rolling.
- A single check result saved in browser `localStorage`, surviving refresh on that browser. Reset is available from the dossier.
- A mock party page, not real multiplayer.

## Known v0.1 limitations

- No logins or cross-device sync; each browser saves its own state.
- No real daily unlock scheduling or secure clue privacy; labels in the app are illustrative.
- This is a static demonstration, not the eventual full four-player web app.

Keep the game behavior and look intact while deploying. Report the repository URL, actual live Pages URL, published commit, and mobile test results to the project owner.
