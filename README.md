# Part Time Work In/Near Guilford

A filterable, single-page job board of part-time openings in and around Guilford, CT —
now covering **Guilford, Madison, Branford, North Branford, and Durham** plus nearby
regional roles (New Haven, North Haven). Targeting start dates June 2026 onward.

One self-contained `index.html` — no build step, no dependencies. Works on GitHub Pages instantly.

## Files
- `index.html` — the site (HTML + CSS + JS, data embedded).
- `jobs-data.json` — the underlying dataset (53 listings) if you want to edit separately.

## Features
- **Tri-state filter pills** — click a Town / Category / Type pill to cycle:
  **off → include** (✓ teal, show only these) **→ exclude** (✕ red strikethrough, hide these)
  **→ off**. Includes and excludes combine across groups; exclude always wins over include.
- **53 job cards** with full metadata: category, employer, town, location, pay, type,
  schedule + hours/week, experience, benefits, posted date, apply method, source.
- **★ Star** good options and **✕ Not interested** to dismiss bad ones — both saved in
  your browser (localStorage), so they persist between visits.
- **"Starred only"** filter to see just your favorites.
- **"Show not interested"** toggle — hidden jobs are removed from view by default; flip
  this on to review or un-hide them.
- Pill filters for **Town**, **Category**, and **Type** (all combinable).
- Free-text search across title / employer / keyword / town.
- Live counts of total shown, starred, and hidden.

## Put it in your repo
From `C:\dev\parttime`:

```bash
git init
git add index.html jobs-data.json README.md
git commit -m "Expanded Guilford-area part-time job board with star/hide"
git branch -M main
git remote add origin https://github.com/AirPengwn/parttime.git
git push -u origin main
```
If the repo already has commits: `git pull origin main --rebase` then `git push`.

## Host free on GitHub Pages
Repo → **Settings → Pages → Source: `main`, root → Save.**
Live at: `https://airpengwn.github.io/parttime/`

## A note on the stars/hides
They live in the browser's localStorage tied to the page's address. They'll persist on the
same browser/device. If you open the file locally (file://) and later via GitHub Pages
(https://), those are two different addresses, so marks won't carry over between them —
pick one home for it and they'll stick.

## Data caveats
Pay is shown as stated in the posting; where a posting only said "hourly," that's noted
rather than guessed. Some municipal postings (Town of Guilford, Durham) rotate or close
quickly — the **View/Apply** link points to the live source so you can confirm before applying.
