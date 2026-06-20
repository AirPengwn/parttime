# Part Time Work In/Near Guilford

A filterable, single-page job board of part-time openings in and around Guilford, CT —
covering **Guilford, Madison, Branford, North Branford, Durham, Clinton, Old Saybrook,
Westbrook, East Haven** and nearby regional roles (New Haven, North Haven, Old Lyme).
Targeting spring/summer 2026 onward.

One self-contained `index.html` — no build step, no dependencies. Works on GitHub Pages instantly.

## Files
- `index.html` — the site (HTML + CSS + JS, data embedded).
- `jobs-data.json` — the underlying dataset (160 listings), regenerated from the embedded array so the two stay in parity.

## Features
- **Tri-state filter pills** — click a Town / Category / Type pill to cycle:
  **off → include** (✓ teal, show only these) **→ exclude** (✕ red strikethrough, hide these)
  **→ off**. Includes and excludes combine across groups; exclude always wins over include.
- **160 job cards** with rich metadata: category, employer, town **+ distance**, pay, type,
  schedule + hours/week, experience, benefits, posted date, apply method, source, and the
  live link.
- **Multi-category tagging** — jobs can carry more than one category. Any role *physically
  at a school* (clerical, cafeteria, custodial, paraeducator, coach…) is automatically also
  tagged **Education**, so it shows up under that filter.
- **Teaching Position filter** — full-time K-12 **Language Arts / English** teaching roles in
  Madison, Branford, North Branford, and Clinton are tagged **Teaching Position** (and
  Education) so you can filter to just them. (Only Language Arts is tracked — no other subjects.)
- **Version + updated stamp** — a `vX.Y.Z` badge after the title and an "updated <date>" note,
  bumped by the daily updater so you can see at a glance when the data last changed.
- **🆕 NEW since last visit** — jobs added since you last opened the board are badged NEW,
  with a "New only" filter and a count. (Driven by a `first_seen` date on each listing and a
  `lastVisit` timestamp saved locally / synced to the cloud.)
- **Highlight chips** — quick scannable perks auto-derived from each listing: 💵 Tips,
  🎁 Bonus, 🏥 Benefits, 🌱 No-experience-OK, 🕐 Flexible, 📅 Weekends, 🌙 Evenings,
  ☀️ Seasonal, 💼 Paid perks, 🏷️ Discount, 🚗 Driving.
- **Expandable details** — each card shows a compact summary; click **Details ▾** to expand
  the full field-by-field breakdown (collapses again with **Hide details**).
- **★ Star** good options and **✕ Not interested** to dismiss bad ones.
- **"Starred only"** filter and a **"Show not interested"** toggle.
- Free-text search across title / employer / keyword / town.
- Live counts of total shown, starred, and hidden.

## Saving your stars & "not interested" marks

Marks are always saved to this browser's **localStorage** (instant, offline). Optionally
they also sync to the cloud via **[JSONBin](https://jsonbin.io)** so they carry across
devices/browsers.

### Turn on cloud sync (JSONBin)
1. Sign up free at <https://jsonbin.io>.
2. Create a bin with any JSON contents, e.g. `{}` — copy its **Bin ID**.
3. **API Keys → create an Access Key** with **Read + Update** permission on that bin, and copy it.
4. Open `index.html`, find the `CLOUD SYNC` block near the top of the `<script>`, and fill in:
   ```js
   const JSONBIN_BIN = "your-bin-id";
   const JSONBIN_KEY = "your-access-key";
   ```
5. Commit & push. The sync chip in the toolbar turns from **Local only** → **Synced**.

**Security note:** this is a *public* page, so anyone viewing source can see those values.
Use a **scoped Access Key** (not your Master Key) — it can only read/write this one bin, i.e.
this job board's stars & hides, never your account. Click the sync chip any time to re-pull
from the cloud. Sync uses last-write-wins on the whole document (fine for a single user
across devices).

## Versioning / push to your repo
This folder is already wired to `https://github.com/AirPengwn/parttime.git` (branch `main`).
Normal flow:
```bash
git add -A
git commit -m "Describe the change"
git push
```

## Host free on GitHub Pages
Repo → **Settings → Pages → Source: `main`, root → Save.**
Live at: `https://airpengwn.github.io/parttime/`

## Data caveats
Pay is shown as stated in the posting; where a posting only said "hourly," that's noted
rather than guessed. Some municipal postings (Town of Guilford, Durham) rotate or close
quickly — the **View/Apply** link points to the live source so you can confirm before applying.
