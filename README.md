# ISSP / MATISSP — content-first port

Modernization of the legacy mathematics course:

- legacy source: `http://users.ift.uni.wroc.pl/~rdurka/matissp/`
- repository: `nowitends/issp_port`
- target site: `https://nowitends.github.io/issp_port/`
- computational language: GNU Octave / MATLAB-compatible code where practical

## Principle

This project does **not** reproduce the old WordPress installation or its visual design.
The WordPress/FTP dump is treated only as an archival source.

The migration preserves and modernizes the useful teaching material:

- mathematical exposition and formulas,
- examples and exercises,
- Octave/MATLAB code,
- meaningful figures and diagrams,
- PDFs, data and downloadable teaching files,
- logical relationships between topics.

WordPress themes, PHP templates, widgets, feeds, comments, archive pages, CSS/JS and other implementation debris are not part of the target course.

## Working model

GitHub Actions are deliberately **not used** in this repository.

Normal work is intentionally simple:

1. edit course files directly in the repository,
2. group related edits into one logical commit,
3. on the local machine run `git pull`,
4. preview the course with `mkdocs serve`,
5. when needed, run the local strict check with `python tools/check_local.py`.

No push to `main` should automatically start a build, audit, crawler, importer, deployment or bot commit.

## Current status

The public course has been reduced to **17 canonical teaching pages**. Mathematical expressions were recovered directly from the original KaTeX source (`span.katex-eq`) and converted to MathJax-compatible Markdown rather than reconstructed from plain text.

The current site also preserves newer materials found in the FTP dump but absent from the old WordPress navigation, including `MatDlaInf-2026.pdf`, `liczby_operacje.pdf`, `pochodne-2026.pdf` and the source Markdown/Marp for the newer derivatives material.

The current course has:

- 17 migrated teaching pages,
- a new landing page and a separate page for newer course material,
- an online-computation guide for GNU Octave Online / MATLAB Online,
- 33 local legacy teaching assets recovered from `www/`,
- a separate supplemental-material set recovered from later uploads,
- 0 unresolved local files from the legacy server,
- an audit of external teaching links,
- a new MkDocs Material site with MathJax, search, responsive navigation, dark/light modes and Octave syntax highlighting.

## Repository layout

```text
content/
  index.md                  new course landing page
  obliczenia_online.md      free browser-based Octave/MATLAB workflow
  materialy_nowsze.md       newer material recovered from the FTP dump
  pages/                    editable canonical Markdown teaching pages
  assets/                   assets used by the new course
  reports/                  migration/reconciliation reports
  site_assets/              new CSS and MathJax configuration

migration/
  content/raw_html/         preserved WordPress entry-content fragments
  content/markdown/         first-pass extracted Markdown
  content/text/             plain-text audit copies
  crawl/                    broad technical crawl of the legacy site
  review/                   extracted/deduplicated archival documents for review

www/                        immutable FTP/WordPress source dump
  wp-content/uploads/       historical uploaded assets
  files/                    fallback folder for manually recovered missing files

audit/                      generated link-health reports
tools/                      extraction, canonicalization and local audit/build scripts
```

## Recovered local legacy files

The six previously missing local teaching files have now been recovered from the archive and published under `content/assets/files/`:

- `Pochodne-2.svg`
- `calki.pdf`
- `Calki-1.svg` (source archive: `Całki-1.svg`)
- `Calki-2.svg` (source archive: `Całki-2.svg`)
- `ODE.pdf`
- `ODE-1.svg`

The four old Koza-hosted dependencies `viete.m`, `rysunki.m`, `kolor.png` and `plot.png` are no longer required by the canonical course. The useful Octave code from the two `.m` examples is already embedded directly in the relevant lesson; the two obsolete screenshots were removed as nonessential external dependencies.

The current local-missing-file count is **0**.

## Legacy import versus editorial source

The initial migration is complete enough that **`content/pages/` is now the editable course source**.

The old WordPress importer is frozen and is never run automatically. A deliberate re-import can still be performed locally with:

```bash
python tools/build_canonical_content.py
python tools/postprocess_canonical.py
python tools/sync_supplemental_assets.py
```

Use this only when intentionally re-importing the archived WordPress state. For normal course development, edit `content/` directly.

`www/` should remain an archival input.

## Building the new site locally

Install the site dependencies once:

```bash
python -m pip install -r requirements-site.txt
```

After pulling repository changes, preview the site locally:

```bash
git pull
mkdocs serve
```

For a strict local production check:

```bash
python tools/check_local.py
```

This runs the course-link audit and then `mkdocs build --strict --clean`. Nothing is submitted to GitHub Actions.

You can also run only the strict MkDocs build:

```bash
mkdocs build --strict --clean
```

## Link audit

`tools/check_course_links.py` checks the canonical pages and writes reports to `audit/`.
It distinguishes successful URLs, genuinely dead/unreachable links and services that merely block automated checks with responses such as HTTP 403/429.

The latest audit has no missing local links in the built canonical site. Legacy references and obsolete external services remain separately listed for editorial cleanup.

## Archival document review

`tools/index_archival_documents.py` inventories PDF/PPTX/Markdown teaching files from the FTP dump, hashes them and extracts searchable text. The current archive contains 18 document files representing 13 unique documents; five are exact duplicates.

This review revealed newer material that was not exposed by the WordPress menu. Such files are staged under `content/assets/supplemental/` and listed on `content/materialy_nowsze.md` rather than being silently merged into older chapters.

## GitHub Pages

There is intentionally no GitHub Actions deployment workflow.

If the public Pages site needs to be updated, build/deploy it deliberately from the local development environment rather than on every repository push. Automatic deployment can be reintroduced later only if it is explicitly wanted.

## Editorial phase

The infrastructure migration is now essentially complete. The next phase is editorial rather than technical:

- merge newer material with older pages where appropriate,
- clean typography and exercise hierarchy,
- replace obsolete external links,
- decide which archival PDFs should become first-class chapters,
- turn selected Octave examples into standalone `.m` files,
- add direct run/open workflows for browser-based Octave and MATLAB Online.
