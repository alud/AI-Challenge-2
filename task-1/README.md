# Task 1 — Leaderboard (Vibe Coding)

A clone of the internal company leaderboard, built without writing code by hand. All real data has been replaced with synthetic Greek-mythology-themed data — no corporate names, photos, titles, or department information were used.

## 🔗 Links

- **Live Demo**: https://alud.github.io/AI-Challenge-2/task-1/
- **Repository**: https://github.com/alud/AI-Challenge-2
- **Source**: [`index.html`](./index.html)
- **Write-up**: [`report.md`](./report.md)

## 🛠 Stack

- **React 18** (via CDN) — UI components and state
- **Tailwind CSS** (via CDN) — styling
- **Babel Standalone** — in-browser JSX compilation
- **Inline SVG icons** — no external icon library
- Single-file `index.html`, **no build step required**

## ✨ Features

- Header with title and subtitle
- Filter bar: Year / Quarter / Category dropdowns + employee search
- Top-3 podium with gold / silver / bronze styling
- Ranked list of all employees with avatar, title, contributions, and total points
- Expandable rows revealing category, period, and contribution details
- Live, real-time filtering and sorting
- Empty state when no employees match the active filters

## 🤖 AI Tooling

Built using **Claude** (Anthropic) as the primary AI assistant, through iterative prompting:
1. Screenshot of the original UI shared as visual reference
2. Component structure agreed on first, code generated after
3. Iterative refinement of styling, interactions, and edge cases
4. Single-file deployment target specified up front to keep things simple

See [`report.md`](./report.md) for the full approach, prompting techniques, and data-replacement strategy.

## 🔒 Responsible AI Usage

In compliance with company policy, **no corporate or personal data was fed into any AI tool**. All names, titles, codes, and photos in the application are synthetic.

## 🚀 Run Locally

Just open `index.html` in any modern browser — no build, no install, no server needed.

```bash
# Optional: serve via a local web server
python3 -m http.server 8000
# Then open http://localhost:8000
```
