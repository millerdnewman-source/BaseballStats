[README.md](https://github.com/user-attachments/files/26223545/README.md)
# ⚾ Baseball Stats Aggregator

A static web app that pulls MLB boxscore data and computes cumulative hitting and pitching stats across a custom list of games. No server, no backend — runs entirely in the browser via the MLB Stats API.

**[Live Demo →](https://yourusername.github.io/your-repo-name)**

---

## How It Works

1. You provide a spreadsheet listing the games you want
2. The app fetches live boxscore data from the MLB Stats API for each game
3. It aggregates stats across all games and displays sortable hitting and pitching tables

---

## Usage

1. Open the GitHub Pages link
2. Prepare your spreadsheet (see format below)
3. Upload it — stats will appear once all games are fetched

---

## Spreadsheet Format

Your file can be `.xlsx`, `.xls`, or `.csv`. No header row is needed. Columns should be in this order:

| Column | Field | Example |
|--------|-------|---------|
| A | *(ignored — use for your own labels)* | Game 1 |
| B | Month name | June |
| C | Day | 14 |
| D | Year | 2024 |
| E | Home team name | Yankees |
| F | Game number (for doubleheaders) | 1 |

> **Note:** The home team name must match the MLB team name — use the city or club name as it appears on MLB.com (e.g. `Yankees`, `Red Sox`, `Cubs`, `White Sox`).

---

## Stats Included

**Hitting:** AVG, OBP, SLG, OPS, H, AB, HR, RBI, 2B, 3B, TB, R, SB, SO, BB, LOB

**Pitching:** IP, ERA, WHIP, K/9, H, ER, R, BB, K, HR, Pitches

---

## Deployment

```bash
# 1. Fork or clone this repo
git clone https://github.com/yourusername/your-repo-name

# 2. The repo only needs one file at the root:
#    index.html

# 3. Enable GitHub Pages:
#    Settings → Pages → Source: main branch / root

# 4. Your app will be live at:
#    https://yourusername.github.io/your-repo-name
```

---

## Notes

- **No data is stored.** Everything runs client-side; nothing is sent to any server.
- **Speed** depends on the number of games. Each game requires two API calls, so larger lists (20+ games) may take 10–20 seconds.
- **OBP formula** currently uses `(H + BB) / (AB + BB)`. Sac flies and HBP are not included since they aren't always available in the boxscore endpoint.
- The app uses the public `statsapi.mlb.com` API, which requires no key and allows browser requests.

---

## Tech Stack

- [MLB Stats API](https://statsapi.mlb.com) — boxscore data
- [SheetJS](https://sheetjs.com) — Excel/CSV parsing in the browser
- [DataTables](https://datatables.net) — sortable, searchable tables
- Vanilla JS, HTML, CSS — no framework, no build step
