# Task 1 — Vibe Coding: Company Leaderboard Clone

## Overview
This task was about building a working application using AI-enhanced tooling and prompting techniques rather than writing code by hand. The goal: replicate the company's internal leaderboard page (UI, filters, sorting, search, podium for top 3, ranked list with expandable rows) — without using any real corporate data.

## Tools Used
- **Claude (Anthropic)** — primary AI assistant for code generation, iterative UI refinement, and synthetic data design.
- **React 18** (via CDN) + **Tailwind CSS** (via CDN) + **Babel Standalone** — single-file `index.html`, no build step, deploys cleanly to GitHub Pages.
- **Inline SVG icons** — no external icon library needed; keeps the file self-contained.
- **GitHub Pages** — static hosting from the repo.

## Approach
1. **Reference capture.** I took a screenshot of the original leaderboard, masked any sensitive details, and shared it with the AI assistant so it could understand the layout (header, filter bar, podium, ranked list).
2. **Component decomposition.** I asked the assistant to break the UI into reusable parts: `FilterDropdown`, `PodiumCard`, `LeaderboardRow`, and the top-level `App`. This made later tweaks easier.
3. **Iterative prompting.** I refined the result in passes — first the structure, then the colors and spacing of the podium (gold/silver/bronze), then the expand/collapse interaction on rows, then the empty-filter state.
4. **Single-file deployment.** To make GitHub Pages deployment trivial (no `npm`, no build), I asked for a single `index.html` using React + Tailwind via CDN. This trades a minor performance cost for zero deployment risk.

## Data Replacement Strategy
The challenge explicitly forbids feeding any corporate data into AI tools — no real names, photos, titles, or department names. My approach:

- **Names**: Greek mythology characters (Athena Pallas, Apollo Helios, Artemis Selene, etc.). Clearly fictional, memorable, and impossible to confuse with real employees.
- **Titles**: Generic industry-standard role names (Senior Software Engineer, Group Manager, Lead QA Engineer, etc.) — these aren't proprietary and would appear at any tech company.
- **Department / location codes**: Replaced the real codes with a fictional scheme — `OL` (Olympus) for the company prefix, `U`/`D`/`G`/`T` for Unit/Department/Group/Team. Same shape as the original (`OL.U1.D1.G1`), but no real organizational structure is leaked.
- **Photos**: No real photos. Avatars are generated as inline SVGs with initials on a colored background — deterministic, lightweight, and obviously synthetic.
- **Scores and contribution counts**: Plausible but invented numbers; not derived from any real data.

This satisfies the "no corporate data" constraint while keeping the leaderboard recognizable as a leaderboard.

## Features Implemented
- Header with title and subtitle.
- Filter bar: All Years / All Quarters / All Categories dropdowns + employee search input.
- Podium for top 3 with gold/silver/bronze styling, rank badges on avatars, points pill, and large rank numerals.
- Ranked list of all employees with avatar, name, title, contribution count, total points, and an expand/collapse chevron.
- Expandable row revealing category, period, and contribution count.
- Live filtering and sorting — all state changes update the podium and list in real time.
- Empty state when no employees match the active filters.

## What I'd Improve With More Time
- Real responsive behavior on small screens (the current layout assumes desktop).
- Animations on filter changes and row expansion.
- Pagination if the dataset grew larger.
- Unit tests around the filter/sort logic.

## Prompting Techniques That Worked
- **Showing, not telling**: A screenshot was worth a thousand words of description.
- **Asking for breakdowns first, code second**: Getting an agreed-on component structure before writing code reduced rework.
- **Tightening the deployment target up front**: Specifying "single-file `index.html`, no build step, must work on GitHub Pages from a subfolder" eliminated whole categories of bugs.
- **Constraint-first data design**: Stating the no-real-data rule before any data was generated led the assistant straight to a thematic synthetic dataset.
