# Canonical MATISSP content

This directory is generated from the **teaching content** of the legacy WordPress site.
It intentionally excludes WordPress/PHP/theme implementation files.

## Current build

- pages: **17**
- local teaching assets copied: **27**
- unresolved local file links: **6**
- external teaching-file dependencies: **54**
- unused candidate files in `www/wp-content/uploads` + `www/files`: **155**

## Layout

- `pages/` — canonical Markdown pages with recovered LaTeX
- `assets/` — only local files actually referenced by current course content
- `reports/missing_local_files.csv` — files to add to `www/files/` if available
- `reports/external_teaching_files.csv` — externally hosted PDFs/scripts/etc. worth archiving locally
- `reports/orphan_asset_candidates.csv` — files present in the dump but not referenced by current public content
- `reports/link_rewrites.csv` — audit trail of rewritten links

`www/` remains the immutable source dump; edit the canonical material under `content/` only after generation.
