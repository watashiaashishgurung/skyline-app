# Skyline: Offline Edition

Skyline is a quick, local (offline) party / classroom game: each round every player still “in” secretly chooses a non‑negative integer. The **lowest unique** guess wins the round. A player can only win once; when all but one have won a special final round is triggered and the game ends.

* **Live Demo:** [GitHub Pages Deployment](https://watashiaashishgurung.github.io/skyline-app/)
* **Created by:** watashiaashishgurung (2024–2025)

---

## 🎮 How to Play
1. Enter the number of players (2–100).
2. Provide each player name.
3. Eligible players (those who have not yet won) enter a guess.
4. The lowest unique guess wins the round; that player “locks in” a win and stops guessing future rounds.
5. Everyone pays the winning guess; the winner receives the whole pot (players × winning guess) and balances adjust.
6. If *no* unique guesses appear, only tied players must re‑enter with a **strictly lower** number (auto‑enforced).
7. When only one player hasn’t won yet a labeled **Final Round** appears; that player submits a single bet and the game ends with a recap.

---

## ✨ Current Feature Set
* **Real‑Time Guess Graph (NEW)** – A smooth animated line chart (Chart.js) plotting every player’s guesses per round for at‑a‑glance trends and pacing. Colors auto‑assign and gaps are spanned where a player no longer guesses.
* **Redo / Re‑Entry Logic** – Automatic detection of “no unique guess” rounds; affected players are forced to input a strictly lower follow‑up guess (input `max` limits plus inline hints).
* **Final Round Auto Detection** – When a single player remains without a win, UI switches to a special final round banner.
* **Pot & Balance Tracking** – All balances update each round (everyone pays; winner receives cumulative pot) with a scoreboard showing wins, balances, and winning round number.
* **Game Log** – Scrollable, emoji‑tagged event log (wins, warnings, re‑entry notices) for transparency and teaching moments.
* **Responsive Retro UI** – Compact pixel/arcade inspired headings, dark theme, keyboard friendly.
* **Offline Friendly** – Pure client‑side logic; load once and keep playing (only external dependency is Chart.js via CDN).
* **Safe Name Handling** – Player names are HTML‑escaped before display.
* **One‑Click Restart** – Clean reset restores initial state and destroys the old chart.

---

## 🆕 What’s New (Latest Update)
| Area | Update |
|------|--------|
| Visualization | Added live multi‑player line graph of guesses for “smooth” visual tracking round‑by‑round. |
| UX | Dynamic hints & input caps during re‑entry rounds (must guess lower than previous). |
| Flow | Automatic switch into clearly labeled Final Round when only one player left. |
| Validation | Stricter integer / non‑negative checks and enforcement of redo constraints. |
| Stability | Minor bug fixes around: (a) clearing redo constraints after a successful round, (b) chart teardown on restart, (c) preventing empty name submissions, (d) ensuring balances update consistently in final round. |
| Accessibility | Improved button labels / contrast and scroll anchoring of log output. |

> Tip: If you want fully offline usage without network, download `index.html` and bundle a local copy of Chart.js; otherwise the CDN link is fine when cached.

---

## 📊 Balances & Scoring
Balances start at 0. Each round:
* Every player (including the winner) pays the winning guess (balance −= guess).
* Winner receives the pot (guess × player count).
* Net effect for the winner that round: `(+ guess * players) - guess`.

The scoreboard shows:
* Player name
* Rounds Won (0/1)
* Current Balance (€)
* The round number they achieved their win

---

## 🚀 Quick Start (Local)
Just open `index.html` in any modern browser (Chrome, Firefox, Edge, Safari). No build step, no server.

---

## 🛠 Tech Notes
* Single self‑contained HTML file with inline `<script>`.
* Uses [Chart.js 4.x] via CDN for the guess timeline.
* Lightweight state model with a `Player` class array; no framework required.
* Graceful restart fully clears object references and destroys the chart instance to avoid stale datasets.

---

## 📄 License
See [LICENSE](LICENSE). Free to use, remix, and share.

---

Enjoy & share with friends. Feedback / issues welcome!
