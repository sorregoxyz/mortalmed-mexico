---
title: "From page to data"
entry: 10
date: 2026-10-19
project: MORTALMED, Mexico subproject
artifact: Building the Specimen
version: v0.1.0-state-of-the-art-1
tags: [infrastructure, CSV, design]
reconstructed: true
---

# 10. From page to data

*2026-10-19. Reconstructed on 2026-10-20 from working notes and conversations.*

## What I did
Separated the data from the page. Entries and relations now live in two CSV files in a `data` folder; the page reads them. Changed the palette to my own colours. Reworked the layout so labels never overlap: each label is measured and kept apart, and the map grows in height instead of squeezing entries against its edges. Text widened to the full page.

## What I noticed
Editing a CSV is a different kind of work from editing a map. It is closer to keeping a register or a herbarium label: one row, one specimen, its source, its status. The map becomes a way of displaying the register rather than the register itself.

## Decisions
- `data/entries.csv`: id, label, short label, category, enactments, to_verify, description, verification note, source, url.
- `data/relations.csv`: source, target, circulation.
- Enactments separated by semicolons; anything to verify marked `yes`.

---
← [[09-2026-10-19-it-all-depends-on-the-amount|It all depends on the amount]] · [[README|Index]] · [[11-2026-10-20-the-map-that-would-not-load|The map that would not load]] →
