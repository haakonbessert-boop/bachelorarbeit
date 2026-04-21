# Anforderungen Bachelorarbeit

## Meilensteine

- **17.04.2026** — Beginn Bearbeitungszeit
- **10.07.2026** — Abgabe (gedrucktes Exemplar + elektronische Beigabe: CD / USB-Stick / Website (GitHub))
- **31.08.–11.09.2026** — Verteidigung (60 Min: 20–30 Min Vortrag + 20–30 Min Fragen)
- **ab 01.06.2026** — Terminvergabe Verteidigung über OPAL

**Note:** 70% aus arithm. Mittel beider Gutachten (abgeschnitten auf 1 Dezimale) + 30% Verteidigung.

---

## SAP / Praxispartner (Janine Steidelmüller)

> Quelle: „KPI Dashboard Interview Summary" — Oliver Timm (22. April 2026)

### Kontext & Problemstellung

SAP Signavio Engineering operiert mit einer fragmentierten Landschaft aus Metriken, Dashboards und Reporting-Tools, die unabhängig voneinander über Teams und Funktionsbereiche entstanden sind. Stakeholder beschreiben täglich Situationen, in denen Daten schwer auffindbar, unvollständig, inkonsistent definiert oder systemübergreifend dupliziert vorliegen. Dominante Themen: **Fragmentierung, fehlende Sichtbarkeit, inkonsistente Datenqualität, Vergleichbarkeit**.

**Ziele des KPI Dashboard Hub (aus Janines Goals):**
- Zentraler Einstiegspunkt für engineering-relevante KPIs
- Echtzeit- oder Near-Realtime-Sichtbarkeit auf Fortschritt, Risiken, operative Signale
- Konsistente KPI-Definitionen und Datenstrukturen
- Reduktion manueller Reporting-Aufwände und Slide-Decks
- Unterstützung von Leadership-Entscheidungen, Priorisierung, Risikoidentifikation
- Förderung von KPI-Literacy quer durch Teams

---

### Bestehende Systemlandschaft (Ist-Zustand)

Aktuell genutzte Systeme (Basis für Kap. 4):

| System | Nutzung | Einschränkungen |
|--------|---------|-----------------|
| SAP Analytics Cloud (SAC) | Zentrale Dashboards | Viele fehlen, veraltet oder langsam; häufige Änderungen |
| ServiceNow | Cloud Health & Reliability, Incident-Metriken | Globale Daten ohne DE |
| Jira (PI) | Flow Metrics, Sprint-Daten, JIRA-Daten | Datenqualität in PI nicht vertrauenswürdig |
| Gainsight | Customer Success (GtM) | — |
| PPR | Unternehmensübergreifendes Reporting | Nur Slides, zu statisch, nicht engineering-spezifisch, groß/wenig hilfreich |
| Product 360 | Produktübersicht | — |
| P&E Fundamentals Dashboard | Engineering-Metriken | — |
| Micro Deliveries | Delivery-Metriken | — |
| DORA | DevOps-Metriken | Kaum noch genutzt |
| Security Dashboards | Sicherheitsmetriken | — |
| Circle CI → Hyperspace Dashboard | CI/CD-Metriken | — |

---

### Herausforderungen (aus Stakeholder-Interviews)

**Datenqualität:**
- „I don't trust the data quality in PI"
- „We are missing about 25% of the data"
- „Poor performance"
- „Some not visible to me"

**Konsistenz & Vergleichbarkeit:**
- Keine Vergleichbarkeit über Epics, Stories, Features hinweg
- Viele verschiedene Produkte, kein Link zum PPR

**Strukturelle Probleme:**
- Häufige Änderungen an CS-Dashboards in SAC
- Fehlende Zuordnung zwischen Systemen
- Fragmentierung → Suchaufwand: „Where do I find what?"

**Transparenz & Kapazität:**
- Fehlende Sichtbarkeit auf Kapazität und Release-Blocker

---

### Funktionale Anforderungen

| # | Anforderung | Priorität |
|---|-------------|-----------|
| F01 | Ein konsolidiertes Dashboard (Single Entry Point) | Hoch |
| F02 | Echtzeit- oder Near-Realtime-Daten | Hoch |
| F03 | Konsistente Datenqualität | Hoch |
| F04 | KPI-Definitionen & Erklärungspanels | Hoch |
| F05 | Filterbarkeit nach Zeiträumen | Mittel |
| F06 | Einfach erweiterbar (neue KPIs, neue Quellsysteme) | Mittel |
| F07 | Cross-Initiative-Sichtbarkeit | Mittel |
| F08 | Einbindung eigener Produktdaten | Mittel |
| F09 | Auffindbarkeit & einfache Navigation | Hoch |
| F10 | Reports mit minimalem Aufwand erstellen | Mittel |
| F11 | State-of-the-art UI | Mittel |

### Nicht-funktionale Anforderungen

| # | Anforderung |
|---|-------------|
| NF01 | Datenintegrität |
| NF02 | Datenkonsistenz |
| NF03 | Zuverlässige Performance |
| NF04 | Usability (selbsterklärend, explorierbar) |
| NF05 | Messbarkeit der Dashboard-Nutzung |
| NF06 | Systemkonsolidierung (nicht weitere Fragmentierung) |

---

### User Stories

**Leadership:**
- Als Leader möchte ich konsistente und vertrauenswürdige Datenqualität, damit ich strategische Entscheidungen auf einer verlässlichen Basis treffe.
- Als EMT-Mitglied möchte ich ein einziges Dashboard statt vieler fragmentierter Systeme, um ohne Suche einen einheitlichen Überblick zu erhalten.
- Als Entscheider möchte ich klare direktionale Orientierung, um Initiativen effektiv steuern zu können.

**Manager:**
- Als Team-Manager möchte ich Unterstützung für Entscheidungen und Priorisierung, um mein Team und Deliverables effektiver zu managen.
- Als Manager möchte ich Echtzeit-Daten, um operative Probleme zeitnah zu erkennen und zu handeln.

**Operative Rollen:**
- Als Contributor möchte ich KPIs leicht auffindbar haben, ohne durch mehrere Dashboards suchen zu müssen.
- Als Nutzer möchte ich klare Erklärungen für Metriken (z.B. Durchschnitt, Median), um Daten korrekt interpretieren zu können.

**Cross-funktionale Teams:**
- Als PM/UX/Ops-Stakeholder möchte ich Sichtbarkeit über Initiativen hinweg, um Abhängigkeiten zu verstehen.

---

### Fehlende KPIs (Stakeholder-Lücken)

**Organisatorisch / Finanziell:**
- Kosten im Vergleich zum eigenen Budget
- Budget-Überblick
- Reisekosten
- Monatlicher Delivery-Output & Trends (kein Überblick über Menge und Art der Items)

**Delivery / Flow / Performance:**
- Velocity / Throughput
- Organisationsweite Performance
- Test Coverage (heute nur Product-Area-weit)

**Innovation & Technologie:**
- Progress with AI

---

### Wichtige KPIs (hoher Stakeholder-Wert heute)

**Customer & Business Value:**
- Retention, Consumed ACV, MAU/DAU/PSAT, Product Usage, Adoption/HEART, Gainsight (Customer Success), Anzahl Customer Reports je Produkt

**Operational Health:**
- Incidents, Ticket Lifetime, Availability, Outages, SLA, Security Findings, Cloud Costs

**Team & Delivery Health:**
- Team Health, Cloud Maturity, DORA/FLOW, AI Advancements, Operational Metrics, Release-relevante Signale

---

### BDC Toolstack — SAP-Referenzarchitektur für KPI-Management (Recherche 21.04.2026)

> Quelle: SAP-interne Recherche (21.04.2026). Relevant für Kap. 6 (Lösungsraum) und Kap. 7 (Scoring-Modell).

**Schicht 1 — Datenbasis & Persistenz**
- **SAP Datasphere:** Zentrale semantische Schicht; KPI-Fakten, Dimensionen, Harmonisierung, Datenprodukte. Primäre persistente Schicht in der BDC. Konnektoren zu SAP- und Non-SAP-Quellen (S/4HANA, HANA Cloud, BW Bridge, BigQuery, Snowflake, Azure SQL, SharePoint u.a.)
- **SAP BW Bridge:** Weiterverwendung bestehender BW-Objekte und -Extraktoren in der Cloud-Architektur

**Schicht 2 — Modellierung, Visualisierung & Monitoring**
- **SAP Analytics Cloud (SAC):** KPI-Modellierung auf Datasphere-Modellen, Stories, "My Metrics"/KPI Monitoring inkl. Alarme, Self-Service-Analyse, Planung

**Schicht 3 — Prozess-KPIs**
- **SAP Signavio Process Insights:** Vordefinierte prozessnahe KPIs und Benchmarks aus operativen Systemen (z.B. S/4HANA); ergänzt klassischen KPI-Stack um Prozesssicht und Actionable Insights

**Ergänzend (ERP-nah)**
- **KPI Workspace (Fiori, App F0818):** Definition und Nutzung von KPI/Evaluationen in S/4HANA-Kontexten

**Rolle von Jira im BDC-Kontext**
Jira ist kein BDC-Tool für KPI-Speicherung/-Berechnung. Es fungiert als externe Quelle für Prozess-/Service-Metriken (z.B. Average Resolution Time, SLA Breach Ratio) — einbindbar über Signavio Process Intelligence/Insights oder Datasphere-Konnektoren.

**Kritischer Fit-Check für Signavio Engineering (eigene Einschätzung)**
Die BDC-Referenzarchitektur ist primär für ERP/S/4HANA-Szenarien konzipiert. Die Signavio-Engineering-Quellsysteme sind jedoch dominant Non-SAP (Jira, ServiceNow, CircleCI, Gainsight). Datasphere kann diese per Konnektoren einbinden, aber Aufwand und Komplexität dieser Integration sind ein zentrales Machbarkeitskriterium für das Scoring-Modell (Kap. 7). → Dieser Reibungspunkt ist ein "erschwerender Faktor im konkreten Einsatzfall" i.S. Sachses Erwartungen.

---

### Empfohlener MVP-Scope (aus Olivers Dokument)

**Im MVP enthalten:**
- Eine konsolidierte Landing Page
- Echtzeit-/Near-Realtime-operative Metriken
- Konsistente KPI-Definitionen
- Basis Customer/Business-KPIs (z.B. Usage, Adoption)
- Cloud-Cost-Sichtbarkeit
- Availability/Outage-Metriken
- Einfache, navigierbare UI
- Klare Dokumentation der Metriken

**Explizit außerhalb MVP (spätere Iteration):**
- Automatisierung Business Operations KPI-View (aktuell monatliches PDF)
- Automatisierung Product-Area-spezifischer Monatsberichte
- KI-basierte Learnings
- Umfangreiche Trend-Bibliotheken

---

## DHSN-Betreuer (Prof. Dr.-Ing. Jürgen Sachse)

> Quelle: Erstgespräch Gutachter — 21. April 2026

### Inhaltliche Erwartungen

- **Entscheidungsmodell ist die zentrale Aufgabe** — nicht nur ein Scoring, sondern methodisch fundierte Entscheidungsfindung
- Methoden aus dem **Software Requirement Engineering** heranziehen (z.B. AHP, gewichtete Bewertungsverfahren, Nutzwertanalyse)
- **Einordnung der Aufgabe:** Wo ist das Problem angelegt? Was macht den konkreten Einsatzfall besonders schwierig?
- Erschwerende Faktoren des Einsatzfalls herausarbeiten (Fragmentierung, RBAC, heterogene Systeme)
- Eventuell eigene Forschungsfrage: Wie wurden **vergleichbare Probleme in anderen Bereichen/Domänen** gelöst?
- **MVP** als artefaktbasierte Evaluation aufbauen
- Verwertbarkeit der Arbeit liegt beim Unternehmen — Praxisnutzen ist zentral
- Forschungsfragen dürfen im Verlauf angepasst werden

### Formales

- KI-Protokollierung wie geplant (KI_PROTOKOLL.md) akzeptiert — kein T1-Log nötig
- Sperrvermerk-Befristung: Entscheidung vertagt
- Feedback-Rhythmus: nach jedem Meilenstein
- **Nächstes Meeting (28. April 2026):** Gliederung und Gedanken dazu vorstellen

---

## Studiengangsleiter (Prof. Hänel)

### Inhalt

| Anforderung | Kapitel | Datei |
|---|---|---|
| Problemstellung + Herleitung; Lösungsrelevanz (Diskrepanz, Hindernisse, Handlungsbedarf) | 1 Einleitung | `chapter/01einleitung.tex` |
| Defizite bestehender Ansätze fundiert herausarbeiten (Literatur, keine internen Docs/Blogs) | 2 Grundlagen & Stand der Forschung | `chapter/02Grundlagen_und_Stand_der_Forschung.tex` |
| Einordnung in die Wirtschaftsinformatik | 1 Einleitung | `chapter/01einleitung.tex` |
| Nachweisführung zur Problemstellung (Ausgangssituation, Systemlandschaft) | 4 Ausgangssituation | `chapter/04Ausgangssituation_und_Systemlandschaft.tex` |
| Eigener Forschungsansatz / Methode (Heinzl + Riedl); Methodik begründen; Ergebniserwartung aufstellen; Literaturrecherche dokumentieren | 3 Methodik | `chapter/03Methodik.tex` |
| Durchführung der Untersuchung | 8 MVP | `chapter/08MVP:Design-Umsetzung_Validierung.tex` |
| Untersuchung der Ergebnisse | 9 Ergebnisse, Diskussion | `chapter/09Ergebnisse_Diskussion.tex` |
| Fazit & Ausblick mit Bezug zur Problemstellung + Zielgruppe | 10 Fazit | `chapter/10Fazit_Ausblick.tex` |
| Alle Aussagen belegen (auch allgemein Bekanntes); ~45 Quellen, Aktualität | durchgängig | alle Kapitel |

### KI-Nutzung

- Zustimmung beider Gutachter einholen (DHSN + Unternehmen) → Dokument unterschreiben lassen (welche Modelle, was)
- LaTeX: Genehmigungsdokument in die Arbeit einbinden
- KI-generierte Stellen als solche kennzeichnen (direkte Übernahme + redigierte Passagen)
- Dokumentation mit Prompts + Ergebnissen beilegen

### Sperrvermerk

- Direkt nach dem Deckblatt platzieren
- Untersagt Veröffentlichung + Zugang zu sensiblen Unternehmensdaten
- Möglicherweise befristet (empfohlen: 1–5 Jahre)
- Unterschrift des Verfassers
