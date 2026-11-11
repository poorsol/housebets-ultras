# Housebets Sportsbook — Master Build v21 (GitHub Pages export)

A standalone static export of the Housebets sportsbook design-contest prototype,
version v21 (the cleaned build: English-only audit plus the leftover fixes).

**This is a design prototype with sample data only.** No real players, no real
money, no backend. All betting interactions run client-side in the browser and
reset when the page is reloaded.

## Contents

- `index.html` — the complete site in one self-contained file: all five pages
  (Sports Home, Live, Football, Match Page, Bet Slip + My Bets), all CSS and
  JavaScript inline, all betting interactions and demo functionality.
- `README.md` — this file.

There are no local images, icons, or other asset files: the design is
typography-led (Anton + Archivo). The only external dependency is the Google
Fonts CDN, which loads Anton and Archivo — no login, no API key, no Muse
runtime. Without internet access the page still works; the fonts fall back to
the system sans-serif stack.

Because the site is a single file with no local asset paths, it works at any
URL path — including a GitHub Pages repository subpath such as
`https://<username>.github.io/<repo>/`. No base-href or path changes are needed.

## What v21 is

v21 is the cleaned build of the Ultras sportsbook prototype:

- English-only copy throughout (audited page by page, including empty states,
  the bet slip, and My Bets); league naming is consistent ("La Liga"
  everywhere).
- Generic AI-style copy rewritten in a real sportsbook voice; dead code and
  duplicated data removed (counts and kick-off lists now come from single
  sources).
- Ultras identity kept: Anton + Archivo, warm paper background, dark ink,
  teal and vermilion accents.
- All betting functionality kept, including the return-block fix: the bet slip
  shows no "To return" block until a selection exists.

## Deploy to GitHub Pages

### Option A — web UI (no git needed)

1. On GitHub, create a new repository (public), e.g. `housebets-sportsbook`.
2. Upload `index.html` and `README.md` to the repository's `main` branch
   (Add file → Upload files), then commit.
3. Go to **Settings → Pages**.
4. Under **Build and deployment → Source**, choose **Deploy from a branch**.
5. Select branch `main` and folder `/ (root)`, then **Save**.
6. After a minute, your site is live at
   `https://<username>.github.io/<repo>/`.

### Option B — git CLI

```bash
git init housebets-sportsbook
cd housebets-sportsbook
cp /path/to/index.html .
cp /path/to/README.md .
git add index.html README.md
git commit -m "Housebets sportsbook v21 (GitHub Pages export)"
git branch -M main
git remote add origin https://github.com/<username>/housebets-sportsbook.git
git push -u origin main
```

Then enable Pages as in steps 3–6 of Option A.

## What to check after deploying

- Open the site at desktop width (1440px) and phone width (390px).
- All five pages are reachable from the top/bottom navigation.
- Bet Slip with nothing selected shows **no** "To return" block; selecting
  Arsenal 1.30 shows "To return 26.00 USDT" at stake 20.
- A placed bet shows Bet ID `HB-2026-1147` and balance 1,010.00 → 990.00.
- Reload the page to reset the demo state (balance, bets, selections).

## Notes

- This export does **not** change the Muse public link, which still serves v16.
  Publishing v21 on Muse (re-share) is a separate step and needs explicit
  approval.
- This repository is not itself a contest submission. The contest form still
  needs the public link plus the Big Idea text, submitted with the entrant's own
  Housebets login before Sat 2026-11-14 18:00 UTC.
- Source version: v21, canonical build sha `bff9b81b…`, built 2026-11-11
  02:58:38 UTC, 77,958-byte `index.html`.
