# KI-Nutzungsprotokoll

Dokumentation aller KI-gestützten Arbeitsschritte gemäß Verpflichtungserklärung (§ 4 des Genehmigungsdokuments).
Gliederung folgt der Kapitelstruktur der Bachelorarbeit; innerhalb jedes Kapitels chronologisch sortiert.

---

## Verwendete Werkzeuge

| Werkzeug | Anbieter | Modell | Einsatzbereich |
|----------|----------|--------|----------------|
| Claude Code (CLI) | Anthropic | Claude Sonnet / Opus | Softwareentwicklung, LaTeX, Visualisierung |
| Claude (claude.ai) | Anthropic | Claude Sonnet / Opus | Textformulierung, Recherche, Strukturierung |

## Nutzungsarten

| Kürzel | Beschreibung |
|--------|-------------|
| **TXT** | Textformulierung — Entwurf oder Überarbeitung von Fließtext |
| **VIS** | Visualisierung — Erstellung von Diagrammen, Abbildungen (TikZ) |
| **DEV** | Softwareentwicklung — Code für MVP, LaTeX-Template, Automatisierung |
| **REC** | Recherche — Literatursuche, Einordnung, Zusammenfassung |
| **STR** | Strukturierung — Gliederung, Kapitelplanung, Outlines |

## Verwendungsklassen

| Klasse | Bedeutung |
|--------|-----------|
| **Direkt** | KI-Ausgabe wurde ohne wesentliche inhaltliche Änderung übernommen |
| **Redigiert** | KI-Ausgabe wurde inhaltlich und/oder sprachlich überarbeitet |
| **Inspiration** | KI-Ausgabe diente als Denkanstoß; Endergebnis ist eigenständig formuliert |

---

## Kapitel 1 — Einleitung

*(noch keine Einträge)*

---

## Kapitel 2 — Grundlagen und Stand der Forschung

*(noch keine Einträge)*

---

## Kapitel 3 — Methodik

### KI-005 | 16.–20. Apr 2026 | STR | Kapitelstruktur und Outline

| Feld | Inhalt |
|------|--------|
| **Werkzeug** | Claude Code (CLI) |
| **Bezug** | Kapitel 3 gesamt — Outline |
| **Prompt (Zusammenfassung)** | Erstelle eine Outline für Kapitel 3 Methodik mit den Subsections 3.1–3.4. Pro Subsection: Hänel-Anforderung, Kernaussagen, Argumentationsstruktur, relevante Quellen, offene Fragen. |
| **Ergebnis (Zusammenfassung)** | Strukturierte Outline in `outline/03-methodik.md` mit Phasen-Mapping-Tabelle (DSRM → Kapitel), Checklisten für 3.2 Literaturrecherche, vorläufigen Kernaussagen für 3.3 Ergebniserwartung. |
| **Verwendung** | **Redigiert** — Gliederung geprüft und an Hänel-Anforderungen abgeglichen, Inhalte ergänzt und umformuliert |

### KI-001 | 20. Apr 2026 | TXT | Fließtext 3.1 Forschungsansatz

| Feld | Inhalt |
|------|--------|
| **Werkzeug** | Claude Code (CLI) |
| **Bezug** | 3.1 Forschungsansatz |
| **Prompt (Zusammenfassung)** | Schreibe Kapitel 3.1 der Bachelorarbeit: Design Science Research als Forschungsansatz begründen. Verwende Heinzl & Riedl (2024) für die DSR-Definition, Hevner et al. (2004) für das IS Research Framework mit Relevance/Rigor Cycle, March & Smith (1995) für die Artefakt-Klassifikation. Grenze DSR von rein empirischen Methoden ab. Bachelorarbeit-gerechte Tiefe (~350 Wörter). |
| **Ergebnis (Zusammenfassung)** | Fließtext mit DSR-Definition, IS Research Framework (3 Sphären, 2 Zyklen), Artefakt-Klassifikation (Modell + Instanz), Abgrenzung zu empirischen Methoden, Quellenrollen. Ca. 350 Wörter. |
| **Verwendung** | **Redigiert** — Struktur und Argumentation geprüft, Formulierungen angepasst, Seitenzahlen als XX-Platzhalter belassen |

### KI-003 | 21. Apr 2026 | VIS | TikZ-Abbildung: IS Research Framework

| Feld | Inhalt |
|------|--------|
| **Werkzeug** | Claude Code (CLI) |
| **Bezug** | 3.1 Forschungsansatz (Abbildung 1) |
| **Prompt (Zusammenfassung)** | Baue die bestehende PNG-Abbildung des IS Research Framework (Hevner et al. 2004) als TikZ-Diagramm in LaTeX nach. Drei Säulen (Environment, IS Research, Knowledge Base), innere Boxen (Development/Build, Justify/Evaluate) mit Assess/Refine-Pfeilen, dicke Pfeile für Relevanz/Rigor, Bottom-Feedback-Pfeile. |
| **Ergebnis (Zusammenfassung)** | TikZ-Diagramm mit expliziten Koordinaten, \fill-Polygonen für die Fat-Arrows, symmetrischen Säulen (je 3.3 cm) und 1.4 cm Lücken. Mehrere Iterationen zur Layout-Optimierung. |
| **Verwendung** | **Redigiert** — Grundstruktur aus KI, Layout und Proportionen in mehreren Runden manuell nachjustiert (Spaltenbreiten, Pfeilpositionen, Label-Platzierung) |

### KI-002 | 21. Apr 2026 | TXT | Fließtext 3.4 Vorgehen im Überblick

| Feld | Inhalt |
|------|--------|
| **Werkzeug** | Claude Code (CLI) |
| **Bezug** | 3.4 Vorgehen im Überblick |
| **Prompt (Zusammenfassung)** | Schreibe Kapitel 3.4: Überblick über das Vorgehen. Mappe die 6 DSRM-Phasen nach Peffers et al. (2007) auf die konkreten Kapitel dieser Arbeit. Ergänze ein TikZ-Prozessdiagramm als Abbildung. Fließtext soll jede Phase kurz erläutern und auf das zugehörige Kapitel verweisen. |
| **Ergebnis (Zusammenfassung)** | Einleitungssatz mit Verweis auf DSRM, 3 Absätze die alle 6 Phasen erläutern (Problemidentifikation → Kommunikation), Kapitelverweise (Kap. 4–10). |
| **Verwendung** | **Redigiert** — Textstruktur beibehalten, Formulierungen überprüft und angepasst, Zitierstil auf \vglcite korrigiert |

### KI-004 | 21. Apr 2026 | VIS | TikZ-Abbildung: DSRM-Phasenmodell

| Feld | Inhalt |
|------|--------|
| **Werkzeug** | Claude Code (CLI) |
| **Bezug** | 3.4 Vorgehen im Überblick (Abbildung 2) |
| **Prompt (Zusammenfassung)** | Erstelle ein TikZ-Prozessdiagramm für die 6 DSRM-Phasen nach Peffers et al. (2007) mit Kapitelzuordnung. Snake-Layout (3+3), Pfeile zwischen den Phasen. |
| **Ergebnis (Zusammenfassung)** | TikZ-Diagramm mit 6 Boxen im Snake-Layout, Pfeilen, Kapitelverweisen. Absolute Koordinaten, text width 3.7 cm. |
| **Verwendung** | **Redigiert** — Layout-Grundstruktur aus KI, Boxgrößen und Abstände manuell angepasst |

---

## Kapitel 4 — Ausgangssituation und Systemlandschaft

*(noch keine Einträge)*

---

## Kapitel 5 — Anforderungsanalyse

*(noch keine Einträge)*

---

## Kapitel 6 — Lösungsraum und Architektur-/Tooloptionen

*(noch keine Einträge)*

---

## Kapitel 7 — Entscheidungs- und Bewertungsmodell

*(noch keine Einträge)*

---

## Kapitel 8 — MVP: Design, Umsetzung und Validierung

*(noch keine Einträge)*

---

## Kapitel 9 — Ergebnisse, Diskussion

*(noch keine Einträge)*

---

## Kapitel 10 — Fazit und Ausblick

*(noch keine Einträge)*

---

## Kapitelübergreifend

*(noch keine Einträge)*
