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

### Formales
- [x] Sperrvermerk: `blockuntil=`-Key in `baarticle.cls` implementiert — Befristungsdatum noch festzulegen
- [ ] KI-Genehmigungsdokument: Platzhalter in `simple.tex` vorbereitet — PDF noch ausstehend (Unterschriften Janine + Jürgen Sachse)
- [x] Typo API-Akronym korrigiert (Applocation → Application)

### Kapitelplanung (aus Exposé)
| # | Kapitel | Geplante Seiten | Status |
|---|---------|-----------------|--------|
| 1 | Einleitung | 4 | Subsections angelegt |
| 2 | Grundlagen und Stand der Forschung | 9 | Subsections angelegt |
| 3 | Methodik | 6 | Subsections angelegt |
| 4 | Ausgangssituation und Systemlandschaft | 7 | Subsections angelegt |
| 5 | Anforderungsanalyse | 7 | Subsections angelegt |
| 6 | Lösungsraum und Architektur-/Tooloptionen | 6 | Subsections angelegt |
| 7 | Entscheidungs- und Bewertungsmodell | 8 | Subsections angelegt |
| 8 | MVP: Design, Umsetzung und Validierung | 8 | Subsections angelegt |
| 9 | Ergebnisse, Diskussion | 5 | Subsections angelegt |
| 10 | Fazit und Ausblick | 2 | Subsections angelegt |

---

## Grober Zeitplan

| Phase | Zeitraum | Schwerpunkt |
|-------|----------|-------------|
| **Orientierung** | 20. Apr – 7. Mai (2,5 Wo.) | Onboarding, Systemlandschaft verstehen, Stakeholder kennenlernen |
| **Anforderungen** | 8. Mai – 24. Mai (2,5 Wo.) | Interviews führen, Anforderungen erheben und priorisieren |
| **Analyse & Modell** | 25. Mai – 14. Jun (3 Wo.) | Lösungsraum analysieren, Scoring-Modell bauen + anwenden |
| **MVP + Schreiben** | 15. Jun – 30. Jun (2,5 Wo.) | MVP umsetzen & validieren, Arbeit fertigstellen |
| **Puffer** | 1. Jul – 9. Jul (10 Tage) | Korrekturen, Feinschliff, unvorhergesehenes |
| **Abgabe** | **10. Jul** | Bachelorarbeit einreichen |
| **Nach Abgabe** | 11. Jul – 30. Sep | Weiterarbeit bei SAP — MVP skalieren, weitere Quellsysteme |

> **Hinweis:** Kapitel 1–3 (Einleitung, Grundlagen, Methodik) sollten parallel zu den frühen Phasen geschrieben werden, nicht erst am Ende.

---

## Offene Fragen (intern)

- [ ] Welche Stakeholder werden konkret für die Anforderungsanalyse interviewt?
- [ ] Wie tief wird die Sensitivitätsanalyse (Kapitel 7 oder 9)?
- [ ] Ist der MVP ein konkretes Tool oder ein Architektur-PoC?
- [ ] Befristungsdatum Sperrvermerk festlegen (Empfehlung: 10. Juli 2029)
- [ ] KI-Genehmigungsdokument: welche Modelle / Tools werden genutzt?

---

## Nächste Schritte

- [ ] KI-Genehmigungsdokument bei Janine Steidelmüller + Dr.-Ing. Jürgen Sachse unterschreiben lassen → als `images/ki-genehmigung.pdf` ins Repo
- [ ] Befristungsdatum Sperrvermerk festlegen → `blockuntil=` in `simple.tex` einkommentieren
- [x] Meeting mit Janine Steidelmüller (Kickoff 20. April)
- [ ] Klärung: Zugang zu Quellsystemen (JIRA, ServiceNow, SAP Analytics Cloud)
- [ ] Klärung: Welche Tools sind SAP-intern zur Nutzung freigegeben?
- [ ] Klärung: Format und Umfang der Stakeholder-Interviews
- [ ] Kapitel 1 (Einleitung) beginnen

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
