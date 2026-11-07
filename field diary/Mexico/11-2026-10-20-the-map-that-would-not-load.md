---
title: "The map that would not load"
entry: 11
date: 2026-10-20
project: MORTALMED, Mexico subproject
artifact: Building the Specimen
version: v0.1.0-state-of-the-art-1
tags: [debugging, infrastructure]
reconstructed: true
---

# 11. The map that would not load

*2026-10-20. Reconstructed on 2026-10-20 from working notes and conversations.*

## What I did
The page loaded on Live Server, but the map stayed empty. The CSV files were correct, in the right place, with the right names.

## What I found
Live Server injects a small reload script into every page, just before `</body>`. My page had no `<body>` tag, because it was written in the format used for published artifacts. So the script was injected inside the map's `<svg>`, and broke the page's own code before it could read the data. No error message appeared, because the code that shows error messages never ran.

## Fixes
- A complete document structure (`<!doctype html>`, `<head>`, `<body>`).
- A local copy of the graph library in `data/`, so the page works offline.
- The version label replaced the theme button: **v0.1.0-state-of-the-art-1**.

## Lesson
Infrastructure is also where things go missing without a trace. The map failed silently, like a regulation that never reaches the counter.

---
← [[10-2026-10-19-from-page-to-data|From page to data]] · [[README|Index]] · [[12-2026-10-20-verifications|Verifications]] →
