# Vorbereitung Hochschul-Sync — Prof. Dr.-Ing. Sachse | 28. April 2026

Thema: Gliederung und Gedanken dazu vorstellen.

---

## Roter Faden

Die Arbeit folgt einer klaren Problem-Lösung-Validierung-Logik:

**Problem verstehen** (Kap. 1–4) → **Anforderungen erheben** (Kap. 5) → **Optionen identifizieren & bewerten** (Kap. 6–7) → **Lösung umsetzen & validieren** (Kap. 8–9) → **Fazit** (Kap. 10)

Jedes Kapitel hat eine definierte Rolle im DSR-Zyklus: Kap. 1–4 sind der Relevance Cycle (Problemraum), Kap. 5–7 der Rigor Cycle (methodische Fundierung + Bewertung), Kap. 8–9 die Evaluation des Artefakts.

---

## Kapitel für Kapitel — Struktur & Begründung

### Kap. 1 — Einleitung (4 S.)
Standardaufbau: Problemstellung → Lösungsrelevanz → WI-Einordnung → Forschungsfrage → Aufbau.
- **1.3 Einordnung in die WI** direkt adressiert Hänels Anforderung; zeigt, dass es sich um ein IS-Problem handelt (heterogene Systemlandschaft, Entscheidungsunterstützung), nicht nur um ein technisches.
- Forschungsfrage bleibt bewusst offen formuliert bis Kap. 3 — kann nach Fortschritt angepasst werden (Sachse, 21.04.).

### Kap. 2 — Grundlagen und Stand der Forschung (9 S.)
Theoretische Basis für alle methodischen Entscheidungen in Kap. 7.
- **2.1 KPI-Management & BI** — definiert zentrale Begriffe; verhindert terminologische Unschärfe im Rest der Arbeit
- **2.2 Enterprise-Systemintegration** — Grundlage für die Lösungsoptionen in Kap. 6
- **2.3 Data Governance & RBAC** — erschwerender Faktor im konkreten Einsatzfall (Sachse: Einordnung der Aufgabe); RBAC ist bei SAP Signavio ein reales Hindernis
- **2.4 Defizite bestehender Ansätze** — Hänel-Anforderung: Problemstellung durch Literatur fundieren, nicht nur durch interne Quellen
- **2.5 Entscheidungsmethoden im Software Engineering** *(neu nach Erstgespräch)* — direkte Umsetzung von Sachses Feedback (21.04.): AHP, Nutzwertanalyse, TOPSIS als Methodenbasis für Kap. 7; theoretische Fundierung der Bewertungsmethodik

### Kap. 3 — Methodik (6 S.)
- **3.1 Forschungsansatz** *(erster Entwurf fertig)* — DSR begründet: Artefakt (Scoring-Modell + MVP) steht im Mittelpunkt; Abgrenzung zu empirischen Methoden
- **3.2 Literaturrecherche** — dokumentiert Rechercheprozess (Hänel: Suchstrategie, Datenbanken, Kriterien); wird erst nach Durchführung geschrieben
- **3.3 Ergebniserwartung** — aufgestellt, bevor das Scoring läuft; dient als Vergleichspunkt für Kap. 9.4
- **3.4 Vorgehen im Überblick** — DSRM-Phasen nach Peffers auf die konkrete Arbeit gemappt; gibt dem Leser Orientierung

### Kap. 4 — Ausgangssituation und Systemlandschaft (7 S.)
Hänel: Nachweisführung zur Problemstellung — Ist-Zustand muss empirisch belegt sein.
- **4.1 Organisatorischer Kontext** — SAP Signavio Engineering als Einheit; Stakeholder, Teamstruktur
- **4.2 Bestehende Systemlandschaft** — die fragmentierten Quellsysteme (SAC, Jira, ServiceNow, Gainsight etc.) im Ist-Zustand
- **4.3 Ist-Zustand KPI-Versorgung** — konkrete Defizite aus Stakeholder-Interviews (Oliver Timms Dokument); quantifiziert das Problem
- **4.4 Datenbereitstellung und Schnittstellenlandschaft** *(neu nach Erstgespräch)* — Janines explizite Anforderung: Datenbereitstellung muss als Thema abgedeckt werden; relevant für Machbarkeitsbeurteilung in Kap. 6
- **4.5 Identifizierte Problemfelder** — Synthese: was genau ist das Problem? (Brücke zu Kap. 5)

### Kap. 5 — Anforderungsanalyse (7 S.)
Methodik aus dem Software Requirement Engineering (Sachses Empfehlung).
- Strukturiertes Vorgehen: Stakeholder identifizieren → Interviews → Requirements priorisieren (MoSCoW oder ähnlich)
- Ergebnis: priorisierte Anforderungsliste als Input für das Scoring-Modell (Kap. 7)

### Kap. 6 — Lösungsraum und Architektur-/Tooloptionen (6 S.)
Identifikation und Vorfilterung der Kandidaten vor der formalen Bewertung.
- **6.1–6.5** je ein Integrationsansatz: Embedding/Föderation, zentrale BI-Aggregation (BDC-Stack), Low-Code/No-Code, Custom Web App — mit technischen Eigenschaften und Einschränkungen
- **6.6 Referenzprojekte** *(neu)* — Janine: es gibt SAP-interne Referenzen; Lessons Learned einarbeiten
- **6.7 Machbarkeitseinschätzung** *(neu)* — Janines Kernkriterium: Umsetzbarkeit als Vorfilter vor dem Scoring; verhindert, dass theoretisch gute aber praktisch unrealistische Optionen ins Scoring einlaufen

### Kap. 7 — Entscheidungs- und Bewertungsmodell (8 S.)
Das zentrale wissenschaftliche Artefakt der Arbeit.
- **7.1 Wahl der Bewertungsmethodik** *(neu nach Erstgespräch)* — Sachses direktes Feedback: Methodenwahl muss begründet sein; Vergleich AHP vs. Nutzwertanalyse vs. qualitative Verfahren → begründete Wahl
- **7.2 Aufbau des Scoring-Modells** — Kriterien aus Kap. 5 abgeleitet, Gewichtung begründet
- **7.3 Bewertung** — transparente Punktevergabe je Option
- **7.4 Ergebnis & Empfehlung** — Gesamtscoring, favorisierte Option
- **7.5 Sensitivitätsanalyse** — Robustheitsprüfung; zeigt wie stabil die Empfehlung bei veränderter Gewichtung ist

### Kap. 8 — MVP: Design, Umsetzung und Validierung (8 S.)
Artefakt 2: prototypische Umsetzung des empfohlenen Ansatzes.
- Scope: konsolidiertes Dashboard für Engineering-KPIs auf Basis des Scoring-Ergebnisses
- Validierung gegen die Anforderungen aus Kap. 5 → schließt den DSR-Zyklus

### Kap. 9 — Ergebnisse und Diskussion (5 S.)
- Beantwortung der Forschungsfrage
- Kritische Reflexion: Was haben wir gelernt? Wo liegen Grenzen?
- **9.4 Vergleich mit Ergebniserwartung** — schließt den Bogen zu Kap. 3.3

### Kap. 10 — Fazit und Ausblick (2 S.)
- Fazit mit explizitem Bezug zur Problemstellung (Hänel-Anforderung)
- Ausblick: nächste Schritte nach dem MVP (Skalierung, weitere Quellsysteme, SAP-interne Verwertbarkeit)

---

## Strukturelle Entscheidungen — zum Erklären

| Entscheidung | Begründung |
|---|---|
| DSR als Methodik | Zwei Artefakte im Zentrum: Scoring-Modell + MVP → passt besser als empirische Studie |
| Kap. 2.5 Entscheidungsmethoden | Direktes Sachse-Feedback (21.04.): theoretische Basis für Kap. 7 nötig |
| Kap. 4.4 Datenbereitstellung | Janine-Anforderung: muss explizit abgedeckt werden |
| Kap. 6.6/6.7 Referenzprojekte + Machbarkeit | Janines Kernkriterium: Umsetzbarkeit; Vorfilter verhindert unrealistische Kandidaten im Scoring |
| Kap. 7.1 Methodenwahl explizit | Sachse: Warum dieses Bewertungsverfahren? — muss begründet sein |

---

## Offene Fragen für Sachse

- Wie tief soll die Sensitivitätsanalyse (Kap. 7.5) gehen — eigener Abschnitt oder kurze Passage?
- MVP: konkretes Tool (z.B. SAC-Dashboard) oder Architektur-PoC? Erwartung von Sachse?
- Forschungsfrage: Ist die aktuelle Formulierung aus dem Exposé noch passend, oder anpassen nach den ersten Erkenntnissen?
