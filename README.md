# PROMPT 2 POSTER

A single-page event website for **PROMPT 2 POSTER** — a prompt-to-poster design challenge hosted at **SES Polytechnic, Solapur**.

Participants are given a theme and must write an original AI prompt on the spot, then turn it into a poster within a strict time limit. The site covers the event overview, schedule, round structure, rulebook, submission guidelines, and judging criteria.

## Tech Stack

- **React 18** — loaded via CDN (no build step, no bundler)
- **Babel Standalone** — in-browser JSX transpilation
- **Vanilla CSS** — custom properties (CSS variables) for theming, no framework

This is a static, dependency-free project. There is no `package.json`, no `npm install`, and no build pipeline — it runs directly in the browser.

## Project Structure

```
.
├── index.html   # Markup, React components (JSX via <script type="text/babel">), and app data
└── style.css    # All styling, including CSS custom properties and responsive rules
```

All React components live inline inside `index.html` and are transpiled in the browser by Babel at load time.

## Running Locally

No installation required. Either:

1. Open `index.html` directly in a browser, **or**
2. Serve the folder with any static file server, for example:
   ```bash
   npx serve .
   ```
   or
   ```bash
   python3 -m http.server
   ```
   then visit `http://localhost:<port>`.

## Sections

| Section | Description |
|---|---|
| Hero | Event title and tagline |
| Event Overview | High-level explanation of the two-step challenge (write the prompt → create the poster) |
| Schedule | Timeline of the day, from arrival to awards |
| Round One / Round Two | Breakdown of each competition round and its phases |
| Prompt Integrity | Rule that prompts must be written live, not prepared in advance |
| Rulebook | Full list of official rules, expandable by clicking each card |
| Submission | Submission guidelines |
| Judging Criteria | The five evaluation categories: Prompt Quality, Creativity, Visual Result, Theme Relevance, Time Discipline |

## Customizing

- **Content** — Event data (schedule, rules, judging criteria) is defined as plain JS objects/arrays near the top of the `<script type="text/babel">` block in `index.html` (e.g. `RULES_DATA`, `JUDGING_DATA`). Edit these directly to change copy.
- **Styling** — Colors, spacing, and typography are controlled by CSS custom properties at the top of `style.css` (e.g. `--ivory`, `--navy`, `--burgundy`).
- **Components** — Each section of the page is its own React function component (`Hero`, `Schedule`, `Rulebook`, `JudgingCriteria`, etc.), making it straightforward to locate and edit a specific part of the page.

## Notes

- The Rulebook cards expand and collapse on click; there is no separate toggle control.
- The site is fully static and can be hosted on any static host (GitHub Pages, Netlify, Vercel, etc.) with no server-side requirements.
