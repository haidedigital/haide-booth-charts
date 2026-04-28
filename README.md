# Haide Booth Charts

Public chart assets for Haide Digital's booth SEO + GEO diagnostics. Files
under `runs/{slug}/` are hotlinked from Notion booth-audit pages via
`https://raw.githubusercontent.com/haidedigital/haide-booth-charts/main/runs/{slug}/{file}.png`.

This repo only contains **rendered charts** — no audit data, no client URLs,
no source code. The full audit pipeline lives in the private
`haide-seo-audits` repo. Each subdir under `runs/` corresponds to a booth
audit run.

Adding a run is automated by the `seo-diagnostics-core` skill:

1. Pipeline converts SVG charts to PNG (`category-pie.png`,
   `severity-bars.png`, `geo-gauge.png`).
2. Pipeline copies them into `runs/{slug}/` here, commits, and pushes.
3. Notion `notion-create-pages` references each PNG via raw URL.

Files are immutable once published — the run slug includes a timestamp so
re-runs always produce a new directory.
