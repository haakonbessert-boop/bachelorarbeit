# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

German-language bachelor thesis (BA Dresden, Wirtschaftsinformatik) on KPI-Hub integration for SAP Signavio. Design Science Research methodology. Main document: `simple.tex`, custom document class: `baarticle.cls`.

## Build

```bash
latexmk -pdf simple.tex          # primary build (thesis)
latexmk -pdf -interaction=nonstopmode simple.tex  # non-stop mode
latexmk -pdf minimal.tex         # minimal template test
latexmk -pdf test.tex            # unit tests (limited)
latexmk -pdf ki-genehmigung.tex  # KI approval form
latexmk -pdf sachse_gliederung.tex  # outline/schedule for advisor
python generate_sachse_docx.py   # regenerate sachse_gliederung.docx (Word export)
```

Glossary uses `\makenoidxglossaries` — no separate indexing step needed. No `.latexmkrc` file; latexmk defaults apply.

Build artifacts (`.aux`, `.log`, `.pdf`, `.synctex.gz`, `.fdb_latexmk`, `.fls`, etc.) do **not** belong in the repo.

## Architecture

- `simple.tex` — main document, loads `acronyms.tex`, `glossary.tex`, `references.bib`
- `baarticle.cls` — BA Dresden document class (margins, spacing, title page, environments). Based on `article` class with `simple` option that auto-loads babel, csquotes, biblatex, hyperref, glossaries
- `baarticle.{bbx,cbx,dbx}` + `ngerman-ba.lbx` — custom biblatex style (author-year-ibid, German). Defines `\vglcite`, `\bacite`, `\captioncite`
- `chapter/01..10*.tex` — thesis chapters (included via `\include{}`)
- `ki-genehmigung.tex` — standalone KI-approval form (separate build)
- `sachse_gliederung.tex` — outline/schedule document for advisor (separate build); `generate_sachse_docx.py` generates the Word version
- `notes/` — project documentation: `THESIS_STATUS.md` (task tracker), `CONVENTIONS.md` (authoritative rules), `MEETINGS.md`, `REQUIREMENTS.md`, `GLOSSAR.md`, `LITERATURE.md`, `KI_PROTOKOLL.md`
- `notes/praxis/` — SAP-context research (tool landscape, system overview)
- `outline/` — chapter planning documents

## Key conventions (authoritative source: `notes/CONVENTIONS.md`)

### Citations

Primary citation command: `\vglcite[PAGE]{key}` — generates footnote with "Vgl.". Always **after** the period: `Text.\vglcite[XX]{key}`. Use `XX` for unknown page numbers.

Other available commands (defined in `baarticle.cbx`):
- `\bacite[PAGE]{key}` — direct citation footnote (without "Vgl.")
- `\captioncite{key}` — inline citation for figure/table source attributes

Never use: `\textcite{}`, `\citet{}`, `\citep{}`, `\autocite{}`. No author names in running text — citations are always anonymous footnotes.

### Glossary / Acronyms

Always use `\gls{key}` for defined terms from `acronyms.tex` and `glossary.tex`. Never write abbreviations manually. When adding a new term: (1) add to `acronyms.tex`/`glossary.tex`, (2) document in `notes/GLOSSAR.md`, (3) use `\gls{key}` in text.

Use `\textit{}` only for terms that have **no** glossary entry (e.g. taxonomy terms like *Modell*, *Instanz*).

### Figures

Use `bafigure` environment with `source=` and `label=`. Prefer TikZ for diagrams. Only include a figure when it is strictly necessary or makes the text understandable without it. Never directly copy figures from publications — redraw and attribute with "in Anlehnung an `\captioncite{key}`".

### Language & style (German academic)

Avoid repetitive self-reference ("diese Arbeit", "die vorliegende Arbeit", "der Autor"). Vary with: "diese Untersuchung", "zu diesem Zweck", passive constructions.

### Git workflow

Commit and push `notes/*.md` and `outline/*.md` files **immediately** after editing. When adding a source: update both `references.bib` and `notes/LITERATURE.md`. Log all AI-assisted work in `notes/KI_PROTOKOLL.md` with running ID (KI-NNN), tool, type (TXT/VIS/DEV/REC/STR), chapter, prompt summary, result, usage class (Direkt/Redigiert/Inspiration).

`notes/THESIS_STATUS.md` is the central task tracker — update "Aktueller Stand" and "Nächste Schritte" after each work session.

## Custom LaTeX environments

- `basimple` — wraps entire thesis (title page, front matter, bibliography, affirmation)
- `bafigure` — figures with frame, auto-caption, source: `\begin{bafigure}[source=..., label=...]{Title}`
- `batable` — same pattern for tables
- `baappx` — appendix with auto-generated list
