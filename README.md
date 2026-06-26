# xG Sandbox — World Cup 2026 ⚽

A small, self-contained web app for exploring **expected-goals (xG) matchups** at the 2026 FIFA World Cup. Pick any two of the 48 teams and the model estimates how the game might go, based on the chances each side has created and conceded so far.

**Live site:** https://YOURUSERNAME.github.io/wc26-xg-sandbox/
*(replace with your URL once GitHub Pages is on)*

---

## ⚠️ Please read first — this is just for fun

This is a **hobby project**, not a prediction service.

- It runs on a **tiny sample** (each team has only played 2–3 games).
- xG on a few matches is **noisy** — a team can look great or terrible for reasons that won't repeat.
- **Do not use this for betting, gambling, or any real-money decision.** The numbers are illustrative and meant for curiosity, not advice.

If you want to wager on football, that's your call — but please don't lean on this toy model to do it.

---

## What it does

- **Pick two teams** (all 48, grouped A–L) and get a win / draw / win estimate.
- **Scoreline ladder** — the most likely results, colour-coded by who benefits.
- **xG panels** — each team's created vs conceded chances, game by game.
- **Form bias slider** — weights recent games more heavily, so an improving team isn't dragged down by a weak opener (and a weakness that *persists* into the latest game still counts).
- **Trend arrows + net-xG trajectory** — see at a glance whether a side is climbing or sliding.
- **"Must win" toggles** — nudge a team's output up to simulate game-state pressure (a team that has to chase the game).
- **Auto "pressure read"** — short notes generated from the numbers (where the edge is, form trajectory, persistent weaknesses, uneven samples).

## How it works (the short version)

Each team's group-stage xG (created and conceded) is averaged, weighted toward recent games. Those feed a **Poisson model** that turns expected goals into a grid of scoreline probabilities. Everything runs **in your browser** — there's no server and no internet call. The data is baked into the file.

## Data & updates

- xG figures come from a public match tracker, used consistently across all 48 teams. Different providers calculate xG slightly differently, so treat the exact decimals loosely.
- The data is a **snapshot** — it does **not** auto-update. After a round of games, the file has to be refreshed by hand (new numbers added, and the structure switched to the knockout bracket once the groups end).

## Tech

One `index.html` file. Plain HTML, CSS, and vanilla JavaScript. No libraries, no build step, no backend. Open it locally or host it anywhere static.

---

*Built for fun during the 2026 World Cup. Not affiliated with FIFA. Not betting advice.*
