# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

German-language bachelor thesis (BA Dresden, Wirtschaftsinformatik) on KPI-Hub integration for SAP Signavio. Design Science Research methodology. Main document: `simple.tex`, custom document class: `baarticle.cls`.

## Build

```bash
latexmk -pdf simple.tex          # primary build
latexmk -pdf -interaction=nonstopmode simple.tex  # non-stop mode
```

Glossary uses `\makenoidxglossaries` — no separate indexing step needed. No `.latexmkrc` file; latexmk defaults apply.

## Architecture

- `simple.tex` — main document, loads `acronyms.tex`, `glossary.tex`, `references.bib`
- `baarticle.cls` — BA Dresden document class (margins, spacing, title page, environments)
- `baarticle.{bbx,cbx,dbx}` + `ngerman-ba.lbx` — custom biblatex style (author-year-ibid, German)
- `chapter/01..10*.tex` — thesis chapters (included via `\include{}`)
- `notes/` — project documentation (status, conventions, glossary, literature, meetings, requirements, AI log)
- `outline/` — chapter planning documents

## Key conventions (authoritative source: `notes/CONVENTIONS.md`)

### Citations

Only citation command: `\vglcite[PAGE]{key}` — generates footnote with "vgl.". Always **after** the period: `Text.\vglcite[XX]{key}`. Use `XX` for unknown page numbers. Never use `\textcite{}`, `\citet{}`, `\citep{}`, `\autocite{}`.

### Glossary / Acronyms

Always use `\gls{key}` for defined terms from `acronyms.tex` and `glossary.tex`. Never write abbreviations manually. When adding a new term: (1) add to `acronyms.tex`/`glossary.tex`, (2) document in `notes/GLOSSAR.md`, (3) use `\gls{key}` in text.

### Figures

Use `bafigure` environment with `source=` and `label=`. Prefer TikZ for diagrams. Redraw from sources with "in Anlehnung an" attribution.

### Git workflow

Commit and push `notes/*.md` files immediately after editing. When adding a source: update both `references.bib` and `notes/LITERATURE.md`. Log all AI-assisted work in `notes/KI_PROTOKOLL.md` with running ID (KI-NNN), tool, type, chapter, prompt summary, result, usage class.

## Custom LaTeX environments

- `basimple` — wraps entire thesis (title page, front matter, bibliography, affirmation)
- `bafigure` — figures with frame, auto-caption, source: `\begin{bafigure}[source=..., label=...]{Title}`
- `batable` — same pattern for tables
- `baappx` — appendix with auto-generated list
