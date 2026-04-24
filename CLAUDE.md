# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

German-language bachelor thesis (BA Dresden, Wirtschaftsinformatik). **Title:** "Ein Mehrkriterien-Entscheidungsmodell zur Auswahl eines KPI-Hub-Integrationsansatzes in einer fragmentierten Enterprise-Systemlandschaft". Topic: KPI-Hub integration for SAP Signavio. Design Science Research methodology. Main document: `simple.tex`, custom document class: `baarticle.cls`.

**Deadline:** 10. Juli 2026 (personal target: 30. Juni 2026). Praxisphase: 20. April – 30. September 2026.

## Build

```bash
latexmk -pdf simple.tex          # primary build (thesis)
latexmk -pdf -interaction=nonstopmode simple.tex  # non-stop mode
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
- `chapter/01..10*.tex` — thesis chapters (included via `\include{}`):
  - 01 Einleitung, 02 Grundlagen und Stand der Forschung, 03 Methodik
  - 04 Ausgangssituation und Systemlandschaft, 05 Anforderungsanalyse
  - 06 Lösungsraum und Architektur-/Tooloptionen, 07 Entscheidungs- und Bewertungsmodell
  - 08 MVP: Design, Umsetzung und Validierung, 09 Ergebnisse und Diskussion, 10 Fazit und Ausblick
- `ki-genehmigung.tex` — standalone KI-approval form (separate build)
- `sachse_gliederung.tex` — outline/schedule document for advisor (separate build); `generate_sachse_docx.py` generates the Word version
- `notes/` — project documentation: `THESIS_STATUS.md` (task tracker), `CONVENTIONS.md` (authoritative rules), `MEETINGS.md`, `REQUIREMENTS.md`, `GLOSSAR.md`, `LITERATURE.md`, `KI_PROTOKOLL.md`
- `notes/praxis/` — SAP-context research: `TOOLS.md` (tool landscape), `KPI_HUB_KONZEPT.md` (KPI Hub concept definition and constraints)
- `outline/` — chapter planning documents
- `Literatur/` — local PDF storage for source papers, organized by chapter (e.g. `03methodik/`, `02Theorie/`); **not tracked in git**

## Key conventions (authoritative source: `notes/CONVENTIONS.md`)

### Citations

Primary citation command: `\vglcite[PAGE]{key}` — generates footnote with "Vgl." for indirect citations. Always **after** the period: `Text.\vglcite[XX]{key}`. Use `XX` as placeholder for unknown page numbers and replace later.

Other available commands (defined in `baarticle.cbx`):
- `\bacite[PAGE]{key}` — direct/verbatim citation footnote (without "Vgl."), only for literal quotes
- `\captioncite{key}` — inline citation for figure/table source attributes (no footnote)

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

## Agent system

All thesis-related tasks **must** be delegated to the specialized agents in `agents/`. Never handle them directly. Read the appropriate agent file(s) from `agents/`, start agent(s) via the Agent tool, and present their results.

| Agent | File | Role |
|-------|------|------|
| Projektmanager | `agents/projektmanager.md` | Schedule, progress, THESIS_STATUS, Feierabend routine |
| Planer | `agents/planer.md` | Chapter structure, argumentation, gap analysis |
| Autor | `agents/autor.md` | Write/revise LaTeX chapter content |
| Rechercheur | `agents/rechercheur.md` | Literature management, citation audit, page numbers |
| Qualitätsprüfer | `agents/qualitaet.md` | Conventions, glossary, language, build check |
| Compliance | `agents/compliance.md` | KI-Protokoll, Git workflow, formalities |
| SAP-Praxis | `agents/sap-praxis.md` | Stakeholders, meetings, system access |
| Redakteur | `agents/redakteur.md` | Repo hygiene, redundancy, consistency |
| Lektor | `agents/lektor.md` | Proofreading, style, argumentation |

Run independent agents in parallel; never run Autor and Qualitätsprüfer on the same chapter simultaneously (write conflicts). Agents cannot cascade — no agent starts another agent.

After each agent call, report to the user: **Agent name → what was done → result → next step**. No silent background work.

If no agent fits a task, tell the user and ask whether to create a new agent.

## Custom LaTeX environments

### `\documentclass` options for `baarticle`

Author identity is set at the class level, not inside `basimple`:

```latex
\documentclass[first=Vorname, last=Nachname, company=Firma, location=Stadt, simple, headertitle=...]{baarticle}
```

`simple` enables the `basimple` environment. `headertitle=` sets the running header (≤80 chars recommended).

### `basimple`

Wraps entire thesis (title page, Sperrvermerk, abstract, front matter, bibliography, affirmation). Key options:

| Key | Purpose |
|-----|---------|
| `img`, `course`, `title`, `number`, `corrector` | Title page fields |
| `themedate`, `returndate`, `signature`, `location` | Dates and signature |
| `type` | Paper type: `thesis`, `study`, or `report` |
| `blockuntil` | Optional Sperrvermerk end date (e.g. `10. Juli 2029`) |
| `kidoc` | Path to signed KI-approval PDF (included via `\includepdf`) |
| `assignment` | Path to thesis assignment PDF |
| `blocknotice` | Boolean, default `true` — set `false` to suppress Sperrvermerk |

The abstract is defined as a `\basimpleabstract` command in the preamble (before `\begin{document}`), not inline.

### `bafigure` / `batable`

`\begin{bafigure}[source=..., label=..., placement=H]{Title}` — framed figure with auto-caption. `batable` uses identical syntax. If `source=` is omitted or empty, both environments auto-add "(Quelle: eigene Darstellung)".

### `baappx`

Appendix with auto-generated Anhangverzeichnis. Figures/tables inside use appendix numbering instead of regular captions.

## Class options and loaded packages

`baarticle.cls` accepts these document class options: `simple` (loads babel, csquotes, biblatex, hyperref, glossaries), `linkcoloring`, `noheader`, `headertitle=...`. The class loads TikZ with libraries: `shapes.geometric`, `shapes.arrows`, `arrows.meta`, `positioning`, `fit`, `backgrounds`.

## Biblatex data model

The `unpublished` entry type auto-appends ", internes Dokument" in the bibliography — use for SAP-internal sources. The `baarticle.dbx` extends the data model with a `bapublisher` field used for `incollection` entries (Hrsg. formatting).
