# Roast Journal ☕

A single-file, mobile-first web app for **Good Cup Academy — Roasting Fundamentals Level 1**.
Plan a roast against a cup target, log milestones live during the roast, measure and cup the
result on 1–5 intensity scales, then compare Target vs. Result and pick ONE adjustment —
the course loop: **Understand → Taste → Plan → Roast → Evaluate → Adjust**.

Everything is saved **in your browser** (localStorage). No account, no backend, no data
leaves the device. Works offline once loaded.

## What it does

- **Identity** — name + team, saved instantly.
- **Roasts** — create roasts with a coffee/batch label; newest first.
- **Roast Plan** — cup target (what do we want in the cup?), charge temp, Phase A/B/C +
  total time targets, end temp, Agtron target, and a control plan.
- **Live Roast Log** — big tap targets for Charge · TP · Color Change · First Crack · Drop.
  Tapping a milestone auto-stamps elapsed time from Charge and lets you enter a temperature.
  A running clock, total time, Phase C duration, and per-phase durations update as you go.
- **Measure** — green/roasted weights with a live weight-loss %, plus actual Agtron.
- **Cup What You Made** — 1–5 intensity scales for acidity, sweetness, bitterness and
  mouthfeel (matching the Participant Guide), plus finish, flavor character, overall, notes.
- **Evaluate** — Target vs. Result side by side, what was different, and ONE thing to
  adjust next time (no scoring, just the course loop).
- **Home** — the landing tab: brand, a one-line intro, the five-part course agenda
  (10:00–18:00 with breaks and lunch), and quick buttons to start a roast or browse the course.
- **Learn** — a scannable contents map of the whole course (the 11 modules in class order,
  grouped by part). Tap any topic to open a **focused, swipeable reader**: one
  concept per screen, swipe left/right (or Prev/Next), a progress indicator, and the notes
  field in context. There's also a **general class notepad** (page 1 of the reader). Every
  slide/topic that has a note shows a dot on the map. All notes flow into the export/print,
  JSON backup, and copy-summary.
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
