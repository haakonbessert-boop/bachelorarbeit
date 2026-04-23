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

### KI-012 | 23. Apr 2026 | TXT | Fließtext 3.3 Ergebniserwartung

| Feld | Inhalt |
|------|--------|
| **Werkzeug** | Claude Code (CLI) |
| **Bezug** | 3.3 Ergebniserwartung |
| **Prompt (Zusammenfassung)** | Schreibe Kapitel 3.3 der Bachelorarbeit: Ergebniserwartung. Typisiere beide Artefakte nach March & Smith (1995) — Bewertungsmodell als Typ Modell, MVP als Typ Instanz. Erkläre die FEDS-Evaluationsstrategie (Venable et al. 2016) für beide Artefakte. Benenne Anforderungsabdeckung nach Cleven et al. (2009) als zentrales Evaluationskriterium. Offene Entscheidungspunkte (Gewichtungsmethodik, Zielsystem MVP) als Vorbehalte formulieren. ~320 Wörter, \vglcite-Zitierstil, \gls{feds} und \gls{ahp} verwenden. |
| **Ergebnis (Zusammenfassung)** | Fließtext ~320 Wörter mit Artefakt-Typisierung, FEDS-Evaluationslogik (formativ/summativ × artifizell/naturalistisch), Anforderungsabdeckung als Hauptkriterium, Vorbehalte zu offenen Entscheidungen. Keine XX-Platzhalter. |
| **Verwendung** | **Redigiert** — Struktur und Argumentationsführung aus KI, inhaltliche Substanz (Artefakttypen, FEDS-Zuordnung, Kriterienkatalog) eigenständig vorgegeben |

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

### KI-010 | 23. Apr 2026 | STR | Glossar-Ergänzung: DAU/MAU + PES

| Feld | Inhalt |
|------|--------|
| **Werkzeug** | Claude Code (CLI) |
| **Bezug** | `acronyms.tex` + `notes/GLOSSAR.md` |
| **Prompt (Zusammenfassung)** | Erkläre DAU/MAU und PES im Signavio-Kontext; übernehme Definitionen in Glossar und Acronyms. |
| **Ergebnis (Zusammenfassung)** | DAU/MAU-Eintrag in GLOSSAR.md erweitert (Stickiness-Erklärung, DAU/MAU-Ratio); PES-Eintrag neu angelegt; `\newacronym{pes}` in `acronyms.tex` ergänzt. |
| **Verwendung** | **Redigiert** — Definitionen aus KI-Erklärung übernommen und in Glossar-Stil gebracht |

### KI-006 | 21. Apr 2026 | REC | BDC/SAP Tool-Landscape-Recherche

| Feld | Inhalt |
|------|--------|
| **Werkzeug** | Claude Code (CLI) |
| **Bezug** | Kap. 4 Systemlandschaft + Kap. 6 Lösungsraum (Vorarbeit) |
| **Prompt (Zusammenfassung)** | Iterative Recherche (3 Runden) zu konkreten SAP-Tools für KPI-Hub: BDC-Stack (Datasphere, SAC, Signavio Process Insights, Integration Suite), EKX Spring Release 2026, Build Work Zone, Cloud ALM. Externe SAP-Quellen abgefragt. Ergänzung durch intern erhaltene BDC-Architekturdetails von Janine. |
| **Ergebnis (Zusammenfassung)** | Dokumentiert in `notes/praxis/TOOLS.md`: BDC-Referenzarchitektur (3-Schichten), EKX als Creation Engine, vollständige Tool-Landscape-Tabelle, Zielarchitektur Signavio Engineering, Critical-Fit-Check. |
| **Verwendung** | **Redigiert** — Recherche-Rohdaten aus KI-Chatbot, Struktur und Bewertung eigenständig; intern ergänzt durch Janines BDC-Hinweise und EKX-Mail |

### KI-007 | 21. Apr 2026 | DEV + VIS | sachse_gliederung.tex (PDF + DOCX für Sachse)

| Feld | Inhalt |
|------|--------|
| **Werkzeug** | Claude Code (CLI) |
| **Bezug** | Projektmanagement — Kommunikation Hochschulbetreuer |
| **Prompt (Zusammenfassung)** | Erstelle ein eigenständiges LaTeX-Dokument (Standalone, kein Thesis-Template) mit Gliederungsübersicht, detaillierter Untergliederung, Rotem Faden (TikZ-Diagramm mit DSR-Phasenzuordnung), Strukturellen Entscheidungen und Zeitplan. Iterative Verbesserungen: gleich große TikZ-Boxen, überspannende DSR-Phasenbeschriftungen, ragged2e für Umbrüche, pandoc-Konvertierung zu DOCX. |
| **Ergebnis (Zusammenfassung)** | `sachse_gliederung.tex` + `sachse_gliederung.pdf` + `sachse_gliederung.docx` — versandfertig für Sachse (nach finaler DOCX-Prüfung morgen). |
| **Verwendung** | **Redigiert** — Layout-Grundstruktur und TikZ aus KI, Inhalte (Kapitelstruktur, Begründungen) eigenständig; mehrere Iterationen zur Qualitätssicherung |

### KI-008 | 22. Apr 2026 | DEV | sachse_gliederung.docx neu generiert (python-docx)

| Feld | Inhalt |
|------|--------|
| **Werkzeug** | Claude Code (CLI) |
| **Bezug** | Projektmanagement — Kommunikation Hochschulbetreuer |
| **Prompt (Zusammenfassung)** | Die pandoc-Konvertierung von LaTeX zu Word zerstört TikZ-Diagramme und komplexe Tabellen. Erstelle ein Python-Script (python-docx) das die sachse_gliederung.docx direkt Word-nativ generiert mit sauberen Tabellen, Textflow-Rotem-Faden und korrekter Formatierung. |
| **Ergebnis (Zusammenfassung)** | `generate_sachse_docx.py` erstellt, generiert `sachse_gliederung.docx` mit Titelblock, Kapitelübersicht, zweispaltiger Detailgliederung, Rotem Faden (Textflow mit Pfeilen + DSR-Phasen), Strukturellen Entscheidungen, Zeitplan. Alles Word-nativ formatiert. |
| **Verwendung** | **Direkt** — Script-Code aus KI, Inhalte identisch zum bestehenden .tex |

### KI-009 | 22. Apr 2026 | STR | Meeting-Vorbereitung und Dokumentation (Svitlana, Oliver)

| Feld | Inhalt |
|------|--------|
| **Werkzeug** | Claude Code (CLI) |
| **Bezug** | Kap. 4 + 6 (Vorarbeit) — Orientierungsphase |
| **Prompt (Zusammenfassung)** | Iterative Unterstützung bei: (1) Umformulierung Svitlana-Meeting-Fragen (von technisch auf Tool-Überblick-Niveau), (2) Auswertung Svitlana-Präsentation "Introducing BDC" (BDC-Architektur, Data Products, Collibra-Rolle), (3) Erfassung Mural-Dashboard-Links, (4) Auswertung #OneDashboard-Dokument (KPI-Kategorien, Initiativen, Hindernisse), (5) Dokumentation aller Meeting-Ergebnisse. |
| **Ergebnis (Zusammenfassung)** | Aktualisierte MEETINGS.md, TOOLS.md (Mural-Overview, Svitlana-Auswertung, #OneDashboard-Analyse, Security-Dashboards, VoC-Bereich), THESIS_STATUS.md. |
| **Verwendung** | **Redigiert** — Strukturierung und Dokumentation durch KI, inhaltliche Inputs und Bewertungen eigenständig |
