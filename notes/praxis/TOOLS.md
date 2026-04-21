# Tools & Systemlandschaft — Praxisphase SAP Signavio

Relevante Tools im Kontext der Praxisphase bei SAP Signavio Engineering.
Für Quellsysteme (Ist-Zustand) → siehe [REQUIREMENTS.md](../REQUIREMENTS.md).

---

## SAP Business Data Cloud (BDC) — Referenzarchitektur

> Quelle: SAP-interne Recherche (21.04.2026). Relevant für Kap. 6 (Lösungsraum) und Kap. 7 (Scoring-Modell).
> Ansprechpartnerin intern: Svitlana Vlasova (s.vlasova@sap.com) — von Janine empfohlen, 21.04.2026

**Schicht 1 — Datenbasis & Persistenz**
- **SAP Datasphere:** Zentrale semantische Schicht; KPI-Fakten, Dimensionen, Harmonisierung, Datenprodukte. Konnektoren zu SAP- und Non-SAP-Quellen (S/4HANA, HANA Cloud, BW Bridge, BigQuery, Snowflake, Azure SQL, SharePoint u.a.)
- **SAP BW Bridge:** Weiterverwendung bestehender BW-Objekte und -Extraktoren in der Cloud-Architektur

**Schicht 2 — Modellierung, Visualisierung & Monitoring**
- **SAP Analytics Cloud (SAC):** KPI-Modellierung auf Datasphere-Modellen, Stories, "My Metrics"/KPI Monitoring inkl. Alarme, Self-Service-Analyse, Planung

**Schicht 3 — Prozess-KPIs**
- **SAP Signavio Process Insights:** Vordefinierte prozessnahe KPIs und Benchmarks aus operativen Systemen; ergänzt klassischen KPI-Stack um Prozesssicht und Actionable Insights

**Ergänzend (ERP-nah)**
- **KPI Workspace (Fiori, App F0818):** Definition und Nutzung von KPI/Evaluationen in S/4HANA-Kontexten

**Rolle von Jira im BDC-Kontext**
Jira ist kein BDC-Tool für KPI-Speicherung/-Berechnung. Fungiert als externe Quelle für Prozess-/Service-Metriken — einbindbar über Signavio Process Intelligence/Insights oder Datasphere-Konnektoren.

**Kritischer Fit-Check für Signavio Engineering**
BDC ist primär für ERP/S/4HANA-Szenarien konzipiert. Signavio-Engineering-Quellsysteme sind dominant Non-SAP (Jira, ServiceNow, CircleCI, Gainsight). Datasphere kann per Konnektoren einbinden, aber Aufwand/Komplexität ist ein zentrales Machbarkeitskriterium (Kap. 7). → "Erschwerender Faktor im konkreten Einsatzfall" i.S. Sachses Erwartungen.
