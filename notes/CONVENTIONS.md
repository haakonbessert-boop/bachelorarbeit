# Arbeitsregeln für Claude in diesem Projekt

Dieses Dokument hält alle Anforderungen und Arbeitsweisen fest, die im Verlauf der Zusammenarbeit festgelegt wurden.

---

## Dateipflege & Git

- **Nach jeder Änderung an `notes/THESIS_STATUS.md`** → sofort committen und pushen
- **Nach jeder Änderung an `notes/MEETINGS.md`** → sofort committen und pushen
- **Nach jeder Änderung an `notes/REQUIREMENTS.md`** → sofort committen und pushen
- **Nach jeder Änderung an `notes/LITERATURE.md`** → sofort committen und pushen
- LaTeX-Build-Artefakte (`.aux`, `.log`, `.pdf`, `.synctex.gz` etc.) gehören **nicht** ins Repo

## Ordnerstruktur

- Alle Notizen liegen unter `notes/`
  - `notes/THESIS_STATUS.md` — Status, Zeitplan, offene Fragen
  - `notes/MEETINGS.md` — alle Meeting-Notizen und Sync-Templates
  - `notes/CONVENTIONS.md` — diese Datei
  - `notes/REQUIREMENTS.md` — Anforderungen nach Quelle (SAP, DHSN, Studiengangsleiter)
  - `notes/GLOSSAR.md` — persönliche Begriffsbasis (Thesis + SAP-Praxiskontext)
  - `notes/LITERATURE.md` — Literaturanalyse (Autor, Relevanz, Key Findings, Kapitel-Mapping)

## Glossar & Abkürzungen

- Beim Erstellen oder Bearbeiten von Texten der Bachelorarbeit neue Fachbegriffe und Abkürzungen **immer gleichzeitig** pflegen:
  1. `notes/GLOSSAR.md` — Begriff mit Definition ergänzen
  2. `acronyms.tex` oder `glossary.tex` — als `\newacronym{}` (Abkürzung) oder `\newglossaryentry{}` (Begriff) eintragen
  3. Im Kapiteltext `\gls{key}` verwenden

## Literatur

- Beim Hinzufügen einer neuen Quelle **immer gleichzeitig** pflegen:
  1. `references.bib` — BibTeX-Eintrag anlegen
  2. `notes/LITERATURE.md` — Analyse-Eintrag mit Relevanz, Kapitel, Key Findings ergänzen

## Inhaltliche Anforderungen

- Änderungen an `notes/THESIS_STATUS.md` und `notes/MEETINGS.md` immer mit konkreten Inhalten befüllen, nicht nur Platzhalter lassen
- Meeting-Notizen in `notes/MEETINGS.md`, nicht in `notes/THESIS_STATUS.md`
