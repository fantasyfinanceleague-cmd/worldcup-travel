# The Long Haul — FIFA World Cup 2026 Group-Stage Travel

An interactive, single-file visualization of how far all 48 national teams travel
during the 2026 World Cup group stage — mapped, ranked, and broken down by what's
forced by the draw versus what comes down to each team's own base-camp choice.

**Live:** _(add your Vercel URL here once deployed)_

---

## What it shows

- **The flight map** — every team's base camp and its three match venues, drawn to scale.
- **Luck of the draw** — a ranking of how spread out each team's three host cities are,
  with no base-camp choices involved (pure geography).
- **The base they should have picked** — each team's travel-minimizing location snapped
  to the nearest real, catalogued elite training facility, with the move shown on a map.
- **Team travel cards** — a shareable per-team summary: total distance, flight hours,
  time zones crossed, minimum rest days, and the tightest match turnaround.
- **The full ranking** — all 48 teams by total distance.

## How the numbers are built

- **Distance** is a one-way sum: for each of a team's three matches, the great-circle
  (haversine) distance from its base camp to the venue, added together. No routing
  assumptions are made.
- **The match schedule** was transcribed from the official FIFA match grid and validated
  four independent ways before use (every match number 1–72 present once, all 48 teams
  with exactly three games, each team within a single group, and venues cross-checked
  against the venue dataset).
- **The "ideal facility"** is the nearest location, from a catalogue of ~155 verified real
  facilities (MLS, USL, Liga MX, CPL grounds; Power-4 university athletic complexes; and
  select prep sites), that minimizes a team's travel — excluding any facility within 25 km
  of one of the team's own match venues. It's framed as the *nearest catalogued* elite base,
  not a claim about every facility that exists.
- **Rest days** use calendar days between consecutive match dates; the "tightest turnaround"
  pairs the shortest gap with the distance traveled across it.

## Data integrity

Every facility in the catalogue is a real, named place with sourced coordinates. Match
dates come from the official schedule, not estimates. Where a figure is an approximation
(e.g. illustrative flight hours), it's labeled as such in the page's methodology section.

## Tech

Plain HTML, CSS, and JavaScript in a single self-contained file — no build step, no
dependencies, no framework. All data is inlined. Maps and charts are hand-built SVG/Canvas.

## Running locally

Open `index.html` in any browser. That's it.

## Deploying

It's a static site. Any static host works (Vercel, Netlify, Cloudflare Pages, GitHub Pages).
On Vercel: import the repo, no build settings needed — it serves `index.html` at the root.
