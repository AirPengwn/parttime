# Part Time Work In/Near Guilford

A filterable, single-page job board of part-time openings in and around Guilford, CT
(start dates targeted for June 2026 onward). Built as one self-contained `index.html`
— no build step, no dependencies. Works on GitHub Pages instantly.

## Files
- `index.html` — the site (HTML + CSS + JS, data embedded). Open it directly or host it.
- `jobs-data.json` — the underlying job dataset, if you want to edit listings separately.

## Features
- Job cards with category, employer, location, pay, type, schedule, summary, and source.
- Pill filters for **category**, **distance**, and **job type** (combinable).
- Free-text search across title / employer / keyword / location.
- Live result count and a "clear all filters" button.
- Dark teal/amber color scheme, responsive grid.

## Put it in your repo
From `C:\dev\parttime` (Command Prompt or PowerShell):

```bash
git init
git add index.html jobs-data.json README.md
git commit -m "Part-time Guilford job board"
git branch -M main
git remote add origin https://github.com/AirPengwn/parttime.git
git push -u origin main
```

If the repo already has commits:
```bash
git pull origin main --rebase
git push
```

## Host it free on GitHub Pages
In the repo on GitHub: **Settings → Pages → Source: `main` branch, root folder → Save.**
Your board goes live at:
`https://airpengwn.github.io/parttime/`

## Updating listings
Edit the cards in `jobs-data.json`, then either re-embed them or just edit the `JOBS`
array near the bottom of `index.html` directly. Each job uses these fields:
`title, employer, category, location, distance, type, pay, schedule, summary, source, url`.

## Notes on the data
Compiled from public listings (Indeed, ZipRecruiter, Glassdoor, Town of Guilford HR,
Guilford Free Library, and employer pages) in late May 2026. Listings change constantly —
the **View / Apply** link on each card points to the live source so you can confirm the
posting is still open before applying. Pay figures are taken from the postings where stated;
where a posting only said "hourly," that's noted rather than guessed.
