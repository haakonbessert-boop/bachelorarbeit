# Bachelorarbeit — Status & nächste Schritte

**Titel:** Ein Mehrkriterien-Entscheidungsmodell zur Auswahl eines KPI-Hub-Integrationsansatzes in einer fragmentierten Enterprise-Systemlandschaft  
**Autor:** Haakon Bessert (3005149)  
**Unternehmen:** SAP SE — Janine Steidelmüller  
**Studiengang:** Wirtschaftsinformatik, BA Dresden  
**Praxisphase:** 20. April – 30. September 2026  
**Abgabe Bachelorarbeit:** 10. Juli 2026 (persönliches Ziel: 30. Juni 2026)

---

## Aktueller Stand (23. April 2026 — Feierabend, 2. Session)

### Struktur
- Exposé: fertig und abgegeben
- Alle 10 Kapitel angelegt mit Subsection-Struktur und Hänel-Anforderungen als Kommentaren
- LaTeX-Template kompiliert fehlerfrei
- Hänel-Anforderungen vollständig in Kapitel-Mapping überführt (siehe [REQUIREMENTS.md](REQUIREMENTS.md))
- **Kapitel 3.1 Forschungsansatz: vollständig geschrieben** (~350 Wörter)
- **Kapitel 3.4 Vorgehen im Überblick: vollständig geschrieben** — DSRM-Phasen auf Kapitel gemappt
- **sachse_gliederung.docx** neu generiert (python-docx), an Janine geschickt → wartet auf Feedback
- **Sachse-Mail** geschrieben, wartet auf Janines OK zum .docx bevor Versand

### Praxisphase (Tag 4)
- Erstgespräch Gutachter (Janine + Sachse, 21.04.) ✓
- Kennenlernen Christopher Pfeiler ✓ → BDC als relevanter nächster Schritt identifiziert
- **Svitlana Vlasova Meeting (22.04.) ✓** → SAC Data Steer, Collibra als fester BDC-Bestandteil, BDC Adoption Program (SharePoint). EKX ihr unbekannt, keine Referenzprojekte. Präsentation ausgewertet.
- **Oliver Timm Check-in (22.04.) ✓** → Mural mit ~25 Dashboard-Links, bis Freitag durcharbeiten. Tool-Übersicht bis 15. Mai. Ich bin das Lead. Persona = Senior Management.
- **#OneDashboard-Dokument** von Oliver ausgewertet → 7 KPI-Kategorien, 5+ parallele Initiativen (teils on hold), Hindernisse dokumentiert
- **SAC-Zugang** erhalten (Data Insights Team) → Signavio Dashboards + Datasphere View-Zugang
- **Mural Dashboard-Analyse (23.04.) ✓** — alle ~25 Links systematisch durchgearbeitet, Befunde in [notes/praxis/TOOLS.md](praxis/TOOLS.md) dokumentiert
- **TOOLS.md vollständig überarbeitet (23.04.)** — thematische Struktur A–H, bereinigt von thesis-opinionierter Sprache
- **KPI_HUB_KONZEPT.md angelegt (23.04.)** — 4-Schichten-Architektur (Datasphere → SAC → Build Work Zone → EKX), Phasenplan, offene Architekturentscheidungen
- **Janine-Sync 24.04. vorbereitet** — Agenda mit Lösungsoptionen, 10 Blockiert-Fragen

### Kernergebnisse Mural-Analyse
- **Fragmentierung bestätigt:** 7 Systeme (SAC, Jira, Collibra, Gainsight, Grafana, Wiki, SharePoint), kein einheitlicher Einstieg
- **RBAC-Problem real:** ~⅓ der Dashboards nicht zugänglich (CAM, EA Store, Sirius-Mitgliedschaft)
- **Stärkste Quellen:** Operational Status Dashboard (ServiceNow), Jira Micro Deliveries
- **Präzedenzfall:** SAP Signavio Product Excellence Portal — existierender Portal-Ansatz, aber nur Product-KPIs, deprecated Komponenten, veraltete Daten

### Neue Erkenntnisse (23.04.)
- **Pendo Analytics Playbook** (Oliver, 23.04.) → Pendo ist bestätigtes Quellsystem für Usage/HEART-KPIs (DAU/MAU, Feature Adoption, Retention, PES). Dokumentiert in TOOLS.md.
- **VoC „One Voice" Alignment Sheet** (Oliver/Janine/Lea Reib, 05.11.2025) → Parallele Initiative mit identischem Problemraum. Kritische Befunde:
  - PPR = aktueller Status quo: 150 Folien (Q2), 5–10 Tage Aufwand — quantifizierter Schmerzpunkt
  - Qualtrics als PSAT-Quelle bestätigt
  - Metabase als neues Tool (Demo-Dashboard „ONE VOICE") — SAP-Freigabe unklar
  - Lea Reib: neue potenzielle Interviewpartnerin
- **Zielarchitektur konkretisiert:** BDC-Stack (Datasphere + SAC) + Build Work Zone (Portal) + EKX (Deliverables optional). Jira + ServiceNow bereits produktiv eingebunden → MVP-Basis ohne neue Integrationen möglich.

### 2. Session (Nachmittag)
- **Agent-System aufgesetzt:** 9 spezialisierte Agents in `agents/` angelegt (Projektmanager, Planer, Autor, Rechercheur, Qualitätsprüfer, Compliance, SAP-Praxis, Redakteur, Lektor)
- **Gesamtcheck (Qualität + Compliance + Redakteur parallel):**
  - 7 LaTeX-Fixes in simple.tex + Kap. 3 (Tippfehler, Zitierkonventionen, `\gls`-Korrekturen, Bandwurmsatz aufgeteilt)
  - GLOSSAR.md: 7 fehlende Abkürzungen ergänzt (DSRM, IS, IT, ACV, DORA, BDC, EKX)
  - .gitignore: .DS_Store ergänzt
  - baarticle.cls: headheight auf 14.5pt (fancyhdr-Warnungen behoben)
- **Repo-Verdichtung:** ~128 Zeilen eingespart (MEETINGS.md leere Templates entfernt, THESIS_STATUS erledigte Blöcke archiviert, KPI_HUB_KONZEPT Redundanzen entfernt, TOOLS.md Aktionspunkte konsolidiert)
- **Methodik-Literatur vervollständigt:**
  - Interview-Methodik-Quelle beschafft: Myers & Newman (2007)
  - BibTeX-Einträge vervollständigt: vombrocke2009 (pages, publisher), cleven2009 (DOI, pages)
  - Key Findings für heinzl2024 in LITERATURE.md nachgetragen
- **Methodik-Literatur-Analyse:** 8/10 Bewertung, Quellenauswahl überdurchschnittlich für BA

### Formales
- [x] Sperrvermerk: implementiert — Befristungsdatum wird erst am Ende der Arbeit geklärt
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
- [x] Referenzprojekte aus anderen SAP-Bereichen anfragen → Svitlana kennt keine; Goals Tracking (Svitlana) als einziges Referenzprojekt identifiziert
- [ ] Methoden aus Software Requirement Engineering für Kap. 2 + 7 recherchieren (AHP, Nutzwertanalyse, TOPSIS)
- [x] Datenbereitstellung als explizites Thema einplanen → Kap. 4.4 angelegt
- [x] Gliederung für nächstes Meeting (28. April) vorbereiten und Sachse vorlegen → .docx an Janine, Mail an Sachse geschrieben

---

## Nächste Schritte (zentrales To-Do-Board)

> Wird nach jedem Meeting / Arbeitsschritt aktualisiert. Fokus auf die aktuelle Phase — nicht zu weit vorausplanen.
> Aktuelle Phase: **Orientierung** (20. Apr – 7. Mai)

### Formales

- [ ] KI-Genehmigungsdokument: Janines Gegenzeichnung ausstehend (siehe Formales oben)
- [x] Svitlana Vlasova anschreiben — Mail gesendet, warte auf Antwort

### Meetings diese Woche

- [x] Erstgespräch Gutachter — Janine + Prof. Dr.-Ing. Sachse | 21. April
- [x] Kennenlernen Christopher Pfeiler | 20. April
- [x] Check-in Oliver Timm — 22. April ✓ → Mural durcharbeiten bis Freitag, Tool-Übersicht bis 15. Mai
- [x] Svitlana Vlasova — BDC/SAC Tool-Überblick | 22. April ✓ → SAC Data Steer, Collibra, BDC Adoption Program (SharePoint) als neue Leads
- [ ] Kennenlernen Nina Vayssiere — 27. April
- [ ] Bei Oliver melden (Anfang nächste Woche, ~27./28.04.): Brauchen wir vor Mai nochmal ein Meeting?

### Zugänge

- [ ] EA Store: **Product 360 Access** + **EVM neue Rolle** → Janine fragen (24.04.)

### Vorbereitung Janine-Sync (✓ Abgeschlossen 23.04.)

- [x] Pendo Analytics Playbook ausgewertet → in TOOLS.md dokumentiert
- [x] One Voice Alignment Sheet ausgewertet → PPR-Schmerzpunkt, Metabase, Lea Reib dokumentiert
- [x] Zielarchitektur konkretisiert → [KPI_HUB_KONZEPT.md](praxis/KPI_HUB_KONZEPT.md)
- [x] Sync-Agenda fertig → MEETINGS.md 24.04. (Stand, Lösungsoptionen, 10 Blockiert-Fragen)
- [ ] Offene Fragen → werden morgen im Sync geklärt (Pendo-Owner, Metabase-Freigabe, Gainsight/Grafana, Qualtrics-API, EA Store, Lea Reib, sachse_gliederung.docx-Freigabe)

### Nächste Woche — Oliver

- [ ] **DORA-Metriken:** Gibt es ein Dashboard dafür? (Deployment Frequency, Lead Time, CFR, MTTR) — größte KPI-Lücke
- [ ] **Security Dashboard Hauptlink** fehlt im Mural — wo ist er?
- [ ] **SAP_Signavio_Dashboards Unterordner** (Jira Dashboards, Product Usage Dashboards) mit Oliver durchgehen
- [ ] Bei Oliver melden (~27./28.04.): Brauchen wir vor Mai noch ein Meeting?

### Schreiben (parallel)

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
| 22.04.2026 | Sperrvermerk-Befristung wird erst am Ende der Arbeit geklärt | Keine Dringlichkeit, Entscheidung hat keine Auswirkung auf Schreibprozess |
| 22.04.2026 | Collibra ist fester Bestandteil des BDC-Stacks (nicht externer Kandidat) | Svitlana-Präsentation: Collibra = offizielle Governance-Plattform im BDC |
| 22.04.2026 | Goals Tracking als Referenzprojekt | Einziges identifiziertes BDC-Projekt mit Engineering-Bezug (Svitlana, Data Products in Collibra → DSP → SAC) |

---

## Archiv erledigter Schritte

### Mural / Dashboard-Analyse (abgeschlossen 23.04.)

- [x] Alle zugänglichen Dashboards durchgegangen: Befunde dokumentiert in [notes/praxis/TOOLS.md](praxis/TOOLS.md)
- [x] Relevante KPIs für KPI-Hub identifiziert, Überlappungen erkannt
- [x] Offene Fragen für Oliver + Janine formuliert (Zugänge, defekte Links)
- [x] Tool-Liste für Janine-Sync fertiggestellt → [KPI_HUB_KONZEPT.md](praxis/KPI_HUB_KONZEPT.md) + MEETINGS.md 24.04.

### Vorbereitung Sachse (abgeschlossen 23.04.)

- [x] sachse_gliederung.docx final durchgehen + Word-Formatierung prüfen → .docx neu generiert (python-docx statt pandoc)
- [x] sachse_gliederung.docx an Janine geschickt (22.04.) — wartet auf Feedback
- [x] Mail an Sachse geschrieben (22.04.) — wartet auf Janines Feedback zum .docx bevor Versand
- [x] KI-Genehmigungsdokument (Sachse-Unterschrift) an Janine weitergeleitet
