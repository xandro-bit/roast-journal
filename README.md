# Roast Journal ☕

A single-file, mobile-first web app for coffee roasting students. Plan a roast, log
milestones live during the roast, record cupping notes, and — on day two — predict a
taste outcome and compare it to what you actually got.

Everything is saved **in your browser** (localStorage). No account, no backend, no data
leaves the device. Works offline once loaded.

## What it does

- **Identity** — name + team, saved instantly.
- **Roasts** — create Day 1 / Day 2 roasts with a label; newest first.
- **Roast Plan** — charge temp, phase (A/B/C) + total time targets, end temp, Agtron target,
  each with a one-line note on what it controls.
- **Live Roast Log** — big tap targets for Charge · TP · DE · First Crack · Drop. Tapping a
  milestone auto-stamps elapsed time from Charge and lets you enter a temperature. A running
  clock and live **DTR** (development time ratio = FC→Drop as a % of total) update as you go.
- **Cupping Notes** — aroma, acidity, sweetness, body, flavor + a 7-segment Jake Hu sweetness
  scale (Grainy → Chocolate) and free notes.
- **Predict → Actual** — Day 2 roasts get a prediction field up top and a side-by-side
  reflection against the cupping notes (no scoring, just reflection).
- **Home** — the landing tab: brand, a one-line intro, the Day 1 / Day 2 class agenda
  (AM/PM), and quick buttons to start a roast or browse the course.
- **Learn** — the two-day course, slide by slide, grouped under collapsible Day/session
  headers (Day 1 morning theory → afternoon roast-to-target; Day 2 morning tasting →
  afternoon roast-for-taste). Each slide carries its talking points and a **per-slide notes
  field**, plus a **general class notepad**. All notes are included in the export/print
  and JSON backup.
- **Export & Print** — printable HTML journal (A4 print stylesheet), JSON backup + import,
  and a plain-text "Copy summary".

## Notes on robustness

- Autosaves (debounced) on every change, with a "Saved ✓" flash.
- The Charge timer stores a timestamp and computes elapsed from `Date.now()`, so it survives
  tab backgrounding.
- Corrupt/empty localStorage falls back to a fresh state.
- 44px+ tap targets; tested at a 375px viewport; functions with no network and no fonts.

## Deploy to GitHub Pages

1. Create a public repo, e.g. `roast-journal`.
2. Add `index.html` to the repo root.
3. **Settings → Pages → Source: Deploy from a branch → `main` / `root` → Save**.
4. Wait ~1 minute. The app is live at:

   ```
   https://<user>.github.io/roast-journal/
   ```

5. Print the QR code below on the student handout / show it in class — it points at the live app.

## QR code

`RoastJournal_QR.png` (in this repo) encodes the live URL
`https://xandro-bit.github.io/roast-journal/` in the course brand colors. Drop it on the
handout or project it in class for students to scan.

![Roast Journal QR](RoastJournal_QR.png)

## Files

- `index.html` — the entire app (HTML + CSS + JS inline). This is all you need.
