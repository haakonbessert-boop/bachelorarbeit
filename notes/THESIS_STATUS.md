# Bachelorarbeit — Status & nächste Schritte

**Titel:** Ein Mehrkriterien-Entscheidungsmodell zur Auswahl eines KPI-Hub-Integrationsansatzes in einer fragmentierten Enterprise-Systemlandschaft  
**Autor:** Haakon Bessert (3005149)  
**Unternehmen:** SAP SE — Janine Steidelmüller  
**Studiengang:** Wirtschaftsinformatik, BA Dresden  
**Praxisphase:** 20. April – 30. September 2026  
**Abgabe Bachelorarbeit:** 10. Juli 2026 (persönliches Ziel: 30. Juni 2026)

---

## Aktueller Stand (21. April 2026 — Feierabend)

### Struktur
- Exposé: fertig und abgegeben
- Alle 10 Kapitel angelegt mit Subsection-Struktur und Hänel-Anforderungen als Kommentaren
- LaTeX-Template kompiliert fehlerfrei
- Hänel-Anforderungen vollständig in Kapitel-Mapping überführt (siehe [REQUIREMENTS.md](REQUIREMENTS.md))
- **Kapitel 3.1 Forschungsansatz: vollständig geschrieben** (~350 Wörter)
- **Kapitel 3.4 Vorgehen im Überblick: vollständig geschrieben** — DSRM-Phasen auf Kapitel gemappt
- **Gliederung + Zeitplan für Sachse:** sachse_gliederung.pdf + sachse_gliederung.docx fertig und gepusht

### Praxisphase (gestartet 20. April)
- Erstgespräch Gutachter (Janine + Sachse, 21.04.) ✓
- Kennenlernen Christopher Pfeiler ✓ → BDC als relevanter nächster Schritt identifiziert
- Tool-Landschaft BDC/SAP recherchiert → [notes/praxis/TOOLS.md](praxis/TOOLS.md)
- EKX als expliziter Tool-Kandidat von Janine erhalten und dokumentiert
- Literatur-PDFs für Kap. 2 + 3 im Repo abgelegt (Literatur/)

### Formales
- [x] Sperrvermerk: implementiert — Befristungsdatum noch offen
- [ ] KI-Genehmigungsdokument: Unterschriften ausstehend (Sachse-Unterschrift erhalten — Janine noch offen)
- [x] KI-Nutzungsprotokoll: läuft

### Kapitelplanung
| # | Kapitel | Geplante Seiten | Status |
|---|---------|-----------------|--------|
| 1 | Einleitung | 4 | Subsections angelegt |
| 2 | Grundlagen und Stand der Forschung | 9 | Subsections angelegt — NEU: 2.5 Entscheidungsmethoden |
| 3 | Methodik | 6 | **3.1 + 3.4 Erster Entwurf** — 3.2–3.3 offen |
| 4 | Ausgangssituation und Systemlandschaft | 7 | Subsections angelegt — NEU: 4.4 Datenbereitstellung |
| 5 | Anforderungsanalyse | 7 | Subsections angelegt |
| 6 | Lösungsraum und Architektur-/Tooloptionen | 6 | Subsections angelegt — NEU: 6.6 Referenzprojekte, 6.7 Machbarkeit |
| 7 | Entscheidungs- und Bewertungsmodell | 8 | Subsections angelegt — NEU: 7.1 Wahl der Bewertungsmethodik |
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
- [ ] Befristungsdatum Sperrvermerk festlegen — wird erst am Ende der Arbeit geklärt
- [x] KI-Genehmigungsdokument: Protokollierung wie geplant (KI_PROTOKOLL.md) akzeptiert — kein T1-Log nötig
- [ ] Referenzprojekte aus anderen SAP-Bereichen anfragen (morgen bei Oliver Timm klären)
- [ ] Methoden aus Software Requirement Engineering für Kap. 2 + 7 recherchieren (AHP, Nutzwertanalyse, TOPSIS)
- [x] Datenbereitstellung als explizites Thema einplanen → Kap. 4.4 angelegt
- [ ] Gliederung für nächstes Meeting (28. April) vorbereiten und Sachse vorlegen

---

## Nächste Schritte (zentrales To-Do-Board)

> Wird nach jedem Meeting / Arbeitsschritt aktualisiert. Fokus auf die aktuelle Phase — nicht zu weit vorausplanen.
> Aktuelle Phase: **Orientierung** (20. Apr – 7. Mai)

### Formales

- [x] KI-Genehmigungsdokument: Sachse-Unterschrift erhalten + an Janine weitergeleitet — Janines Gegenzeichnung ausstehend
- [ ] Befristungsdatum Sperrvermerk — wird erst am Ende der Arbeit geklärt
- [x] Svitlana Vlasova anschreiben — Mail gesendet, warte auf Antwort

### Meetings diese Woche

- [x] Erstgespräch Gutachter — Janine + Prof. Dr.-Ing. Sachse | 21. April
- [x] Kennenlernen Christopher Pfeiler | 20. April
- [x] Check-in Oliver Timm — 22. April ✓ → Mural durcharbeiten bis Freitag, Tool-Übersicht bis 15. Mai
- [x] Svitlana Vlasova — BDC/SAC Tool-Überblick | 22. April ✓ → SAC Data Steer, Collibra, BDC Adoption Program (SharePoint) als neue Leads
- [ ] Kennenlernen Nina Vayssiere — 27. April
- [ ] Bei Oliver melden (Anfang nächste Woche, ~27./28.04.): Brauchen wir vor Mai nochmal ein Meeting?

### Vorbereitung Sachse (28. April — Mail statt Meeting)

- [x] sachse_gliederung.docx final durchgehen + Word-Formatierung prüfen → .docx neu generiert (python-docx statt pandoc)
- [x] sachse_gliederung.docx an Janine geschickt (22.04.) — wartet auf Feedback
- [x] Mail an Sachse geschrieben (22.04.) — wartet auf Janines Feedback zum .docx bevor Versand
- [x] KI-Genehmigungsdokument (Sachse-Unterschrift) an Janine weiterleitet

### Schreiben (parallel starten)

- [ ] Literaturrecherche Methodik starten (Einstieg: Hevner et al. 2004, Peffers 2007) — Seitenzahlen für XX-Platzhalter in Kap. 3.1 + 3.4 nachtragen
- [x] Kapitel 3.1 Forschungsansatz — Erster Entwurf
- [x] Kapitel 3.4 Vorgehen im Überblick — Erster Entwurf
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
| 21.04.2026 | KI-Protokollierung wie geplant akzeptiert | Sachse akzeptiert KI_PROTOKOLL.md — kein T1-Log nötig |
| 21.04.2026 | Machbarkeit als zentrales SAP-Kriterium | Janine: Umsetzbarkeit ist der SAP am allerwichtigsten |
| 21.04.2026 | Entscheidungsmethodik aus Software Req. Engineering | Sachse: Methoden wie AHP, Nutzwertanalyse für Kap. 7 heranziehen |
| 21.04.2026 | Forschungsfragen dürfen angepasst werden | Sachse: Anpassung nach Fortschritt erlaubt |
| 21.04.2026 | Gliederung erweitert: 2.5, 4.4, 6.6/6.7, 7.1 neu | Umsetzung Erstgespräch-Feedback (Entscheidungsmethoden, Datenbereitstellung, Machbarkeit, Methodenwahl) |
