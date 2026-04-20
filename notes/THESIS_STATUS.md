# Bachelorarbeit — Status & nächste Schritte

**Titel:** Ein Mehrkriterien-Entscheidungsmodell zur Auswahl eines KPI-Hub-Integrationsansatzes in einer fragmentierten Enterprise-Systemlandschaft  
**Autor:** Haakon Bessert (3005149)  
**Unternehmen:** SAP SE — Janine Steidelmüller  
**Studiengang:** Wirtschaftsinformatik, BA Dresden  
**Praxisphase:** 20. April – 30. September 2026  
**Abgabe Bachelorarbeit:** 10. Juli 2026 (persönliches Ziel: 30. Juni 2026)

---

## Aktueller Stand (20. April 2026)

### Struktur
- Exposé: fertig und abgegeben
- Alle 10 Kapitel angelegt mit Subsection-Struktur und Hänel-Anforderungen als Kommentare
- LaTeX-Template kompiliert fehlerfrei
- Hänel-Anforderungen vollständig in Kapitel-Mapping überführt (siehe [REQUIREMENTS.md](REQUIREMENTS.md))
- **Kapitel 3.1 Forschungsansatz: vollständig geschrieben** (~350 Wörter, bachlorarbeit-gerechte Tiefe)
  - DSR-Definition, IS Research Framework (Relevance/Rigor Cycle), Artefakt-Klassifikation nach March & Smith, Abgrenzung zu empirischen Methoden, Quellenrollen
  - Abbildung IS Research Framework eingebunden (`images/IS_Research.png`)
  - Labels für 3.2 (`\label{sec:literaturrecherche}`) und 3.4 (`\label{sec:vorgehen}`) gesetzt

### Formales
- [x] Sperrvermerk: `blockuntil=`-Key in `baarticle.cls` implementiert — Befristungsdatum noch festzulegen
- [ ] KI-Genehmigungsdokument: Platzhalter in `simple.tex` vorbereitet — PDF noch ausstehend (Unterschriften Janine + Jürgen Sachse)
- [x] Typo API-Akronym korrigiert (Applocation → Application)
- [x] IT und IS in `acronyms.tex` ergänzt
- [x] LaTeX-Schreibkonventionen in `notes/CONVENTIONS.md` dokumentiert

### Kapitelplanung (aus Exposé)
| # | Kapitel | Geplante Seiten | Status |
|---|---------|-----------------|--------|
| 1 | Einleitung | 4 | Subsections angelegt |
| 2 | Grundlagen und Stand der Forschung | 9 | Subsections angelegt |
| 3 | Methodik | 6 | **3.1 fertig** — 3.2–3.4 offen |
| 4 | Ausgangssituation und Systemlandschaft | 7 | Subsections angelegt |
| 5 | Anforderungsanalyse | 7 | Subsections angelegt |
| 6 | Lösungsraum und Architektur-/Tooloptionen | 6 | Subsections angelegt |
| 7 | Entscheidungs- und Bewertungsmodell | 8 | Subsections angelegt |
| 8 | MVP: Design, Umsetzung und Validierung | 8 | Subsections angelegt |
| 9 | Ergebnisse, Diskussion | 5 | Subsections angelegt |
| 10 | Fazit und Ausblick | 2 | Subsections angelegt |

---

## Grober Zeitplan

> **Wichtig:** Schreiben läuft **parallel zu jeder Phase** — nicht erst am Ende. Die "MVP + Schreiben"-Phase hat nur 2,5 Wochen, das reicht nicht für 60 Seiten. Jede Phase hat ein Schreibziel.

| Phase | Zeitraum | Inhaltlicher Schwerpunkt | Parallel schreiben |
|-------|----------|--------------------------|--------------------|
| **Orientierung** | 20. Apr – 7. Mai | Onboarding, Systemlandschaft, Stakeholder kennenlernen | Kap. 3 Methodik (DSR steht fest) + Kap. 1 Einleitung (Problemstellung) + **Literaturrecherche starten** |
| **Anforderungen** | 8. Mai – 24. Mai | Interviews führen, Requirements erheben und priorisieren | Kap. 2 Grundlagen & Stand der Forschung + Kap. 4 Ausgangssituation |
| **Analyse & Modell** | 25. Mai – 14. Jun | Lösungsraum analysieren, Scoring-Modell bauen + anwenden | Kap. 5 Anforderungsanalyse + Kap. 6 Lösungsraum + Kap. 7 Entscheidungsmodell |
| **MVP** | 15. Jun – 30. Jun | MVP umsetzen & validieren | Kap. 8 MVP + Kap. 9 Ergebnisse + Kap. 10 Fazit |
| **Puffer** | 1. Jul – 9. Jul | — | Korrekturen, Feinschliff, Roter-Faden-Check |
| **Abgabe** | **10. Jul** | — | — |
| **Nach Abgabe** | 11. Jul – 30. Sep | Weiterarbeit bei SAP — MVP skalieren, weitere Quellsysteme | — |

### Literaturrecherche

- **Jetzt sofort beginnen** — parallel zum Onboarding
- Pflicht-Einstieg: Hevner et al. (2004) — Design Science Research in Information Systems
- Weitere Kernthemen: Enterprise BI-Integration, KPI-Dashboards, RBAC in Enterprise-Systemen, Föderations-Architektur
- Rechercheprozess dokumentieren (Hänel-Anforderung: Suchstrategie, Datenbanken, Ein-/Ausschlusskriterien) → fließt in Kap. 3

> **Hinweis:** Kapitel 1–3 (Einleitung, Grundlagen, Methodik) sollten parallel zu den frühen Phasen geschrieben werden, nicht erst am Ende.

---

## Offene Fragen (intern)

- [ ] Wie tief wird die Sensitivitätsanalyse (Kapitel 7 oder 9)?
- [ ] Ist der MVP ein konkretes Tool oder ein Architektur-PoC?
- [ ] Befristungsdatum Sperrvermerk festlegen (Empfehlung: 10. Juli 2029)
- [ ] KI-Genehmigungsdokument: welche Modelle / Tools werden genutzt?

---

## Nächste Schritte (zentrales To-Do-Board)

> Wird nach jedem Meeting / Arbeitsschritt aktualisiert. Fokus auf die aktuelle Phase — nicht zu weit vorausplanen.
> Aktuelle Phase: **Orientierung** (20. Apr – 7. Mai)

### Formales

- [ ] KI-Genehmigungsdokument bei Janine + Prof. Dr.-Ing. Sachse unterschreiben lassen (Erstgespräch 21. Apr)
- [ ] Befristungsdatum Sperrvermerk klären (Erstgespräch 21. Apr)

### Meetings diese Woche

- [ ] Erstgespräch Gutachter — Janine + Prof. Dr.-Ing. Sachse | 21. April 13:30
- [ ] Check-in Oliver Timm — 22. April
- [ ] Kennenlernen Nina Vayssiere — 27. April

### Schreiben (parallel starten)

- [ ] Literaturrecherche Methodik starten (Einstieg: Hevner et al. 2004, Peffers 2007) — Seitenzahlen für XX-Platzhalter in Kap. 3.1 nachtragen
- [x] Kapitel 3.1 Forschungsansatz geschrieben
- [ ] Kapitel 3.4 Vorgehen im Überblick (nächster Schritt — eng verzahnt mit DSRM-Phasen nach Peffers)
- [ ] Kapitel 3.3 Ergebniserwartung (wenn Kap. 7 klarer ist)
- [ ] Kapitel 3.2 Literaturrecherche (erst nach Durchführung der Recherche)

---

## Meeting-Struktur

### Sync mit Janine Steidelmüller (SAP) — wöchentlich
**Agenda-Template:**
- Was habe ich seit letztem Sync gemacht?
- Was ist als nächstes geplant?
- Wo brauche ich Input / bin ich blockiert?
- Offene Fragen

### Sync mit Hochschulbetreuer — alle 2 Wochen
**Agenda-Template:**
- Aktueller Stand Bachelorarbeit (Kapitel, Seitenanzahl)
- Methodische oder inhaltliche Fragen
- Feedback zu Zwischenständen
- Nächste Meilensteine bis zum nächsten Termin

---

## Meeting-Notizen

→ Siehe [MEETINGS.md](MEETINGS.md)

---

## Entscheidungslog

| Datum | Entscheidung | Begründung |
|-------|-------------|------------|
| Apr 2026 | Design Science Research als Methodik | Artefakt (Scoring-Modell + MVP) steht im Mittelpunkt, keine reine Beschreibung |
| Apr 2026 | Einschränkung auf SAP-intern freigegebene Tools | Praxisbezug und beherrschbarer Scope |
| Apr 2026 | Kapitel-Struktur nach Hänel-Anforderungen ausgerichtet | Anforderungen direkt als Kommentare in Subsections verankert |
