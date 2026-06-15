# RafiFinance

A complete personal finance tracker built as a **single HTML file** — no npm, no build step, no server. Open it in a browser and it just works. Available as a PWA installable on Android and iOS.

🔗 **Live:** [finance.rafiarsya.com](https://finance.rafiarsya.com)

---

## Features

- **Transactions** — Log income and expenses with category, date, and notes
- **Budget Tracking** — Monthly budgets per category with visual progress bars
- **Saving Goals** — Set a target and deadline; auto-calculates required monthly savings
- **Recurring Reminders** — Browser notifications for bills and subscriptions
- **6-Month Analysis** — Visual income vs expense trends with spending breakdown
- **Financial Health Score** — Real-time 0–100 score based on savings rate, budget adherence, and goal progress
- **Export / Import** — Full data export as JSON; import on any device instantly
- **PWA** — Installable on Android and iOS, works fully offline

---

## Tech Stack

| Layer | Tech |
|---|---|
| Frontend | Vanilla JavaScript (ES2022) |
| Styling | CSS Custom Properties, dark theme |
| Icons | Lucide (CDN) |
| Fonts | Inter + JetBrains Mono |
| Storage | localStorage (`rfv4`) |
| PWA | Web App Manifest + Service Worker |
| Hosting | Cloudflare Pages |

---

## Architecture

Everything lives in **one HTML file** — HTML structure, 800+ lines of CSS, and 1800+ lines of vanilla JS. No framework, no build pipeline, no dependencies.

```
rafifinance/
├── index.html      # The entire app
├── manifest.json   # PWA manifest
├── sw.js           # Service worker (offline support)
└── icon-*.png      # App icons (72 → 512px)
```

State is managed with a single global object persisted to `localStorage` under the key `rfv4`. Export/import as JSON anytime.

---

## Financial Health Score

The score (0–100) is computed from three weighted signals:

```js
// Savings Rate   (40%) — target ≥ 20% savings rate
// Budget Adherence (35%) — % of budgets within limit
// Goal Progress  (25%) — average progress toward saving goals
```

---

## PWA Install

**Android:** Open [finance.rafiarsya.com](https://finance.rafiarsya.com) in Chrome → tap the install banner or Menu → *Add to Home Screen*

**iOS:** Open in Safari → Share → *Add to Home Screen*

---

## Local Usage

No installation needed — just open the file:

```bash
# Clone
git clone https://github.com/rafiarsya07/rafifinance.git
cd rafifinance

# Open directly in browser
open index.html   # macOS
start index.html  # Windows
```

Or serve locally:

```bash
python3 -m http.server 8080
# Visit http://localhost:8080
```

---

## Data Privacy

All data is stored **locally on your device** in `localStorage`. Nothing is sent to any server. Export your data anytime as a JSON file for backup or migration.

---

## License

MIT — do whatever you want with it.

---

*Built by [Muhammad Rafi Arsya](https://rafiarsya.com)*
