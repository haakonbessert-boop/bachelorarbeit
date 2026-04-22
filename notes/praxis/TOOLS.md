# Tools & Systemlandschaft — Praxisphase SAP Signavio

Relevante Tools im Kontext der Praxisphase bei SAP Signavio Engineering.
Für Quellsysteme (Ist-Zustand) → siehe [REQUIREMENTS.md](../REQUIREMENTS.md).

---

## SAP Business Data Cloud (BDC) — Referenzarchitektur

> Quellen: SAP-interne Recherche (21.04.2026) + EKG-Recherche via KI (21.04.2026).
> Relevant für Kap. 6 (Lösungsraum) und Kap. 7 (Scoring-Modell).
> Ansprechpartnerin intern: Svitlana Vlasova (s.vlasova@sap.com) — von Janine empfohlen, 21.04.2026

### Zielarchitektur (Schichten)

**Schicht 1 — Datenbasis & Persistenz**
- **SAP Datasphere:** Zentrale semantische Schicht; KPI-Fakten, Dimensionen, Harmonisierung, Datenprodukte. Primäre persistente Schicht der BDC.
- **SAP BW Bridge:** Weiterverwendung bestehender BW-Objekte/-Extraktoren in der Cloud-Architektur

**Schicht 2 — Modellierung, Visualisierung & Monitoring**
- **SAP Analytics Cloud (SAC):** KPI-Modellierung auf Datasphere-Modellen, Stories, "My Metrics"/Watchlist inkl. Alarme, Self-Service-Analyse, Planung

**Schicht 3 — Prozess-/Service-KPIs**
- **SAP Signavio Process Insights:** Vordefinierte prozessnahe KPIs und Benchmarks; Jira + ServiceNow sind als Quellsysteme geführt (Metriken z.B. Average Resolution Time, Breached SLA Ratio, Total Open Issues)

**Ergänzend (ERP-nah, für Signavio Engineering nicht primär relevant)**
- **KPI Workspace (Fiori, App F0818):** KPI-Definition in S/4HANA-Kontexten

---

### Konnektivität Non-SAP-Quellen (EKG-Befund)

Keine dedizierten Out-of-the-box-Konnektoren für Jira, ServiceNow, CircleCI, Gainsight in Datasphere belegt. Realistische Integrationspfade:

| Quelle | Empfohlener Pfad | Reife |
|--------|-----------------|-------|
| Jira | REST API (Datasphere Replication Flows) oder Signavio-Adapter | REST: Roadmap/Feature; Signavio: produktiv |
| ServiceNow | REST API (Replication Flows) oder Signavio-Adapter | REST: Roadmap/Feature; Signavio: produktiv |
| CircleCI | REST API (Build/Pipeline/Test-Reports) oder File-Export | REST: Roadmap/Feature |
| Gainsight | REST API oder File-Export | REST: Roadmap/Feature |

**Generische Integrationspfade:**
- **REST API via Replication Flows** — im EKG als Roadmap-/Feature-Item nachgewiesen; in Kundenprojekten produktiv nutzbar wenn API-Limits, Paginierung, Delta-Logik und Retry/Backoff sauber gelöst sind
- **File/Object Store Staging** — periodische Exporte (CSV/Parquet) als robuster Fallback; von Datasphere einlesbar

**Schnellster Weg für Issue-/ITSM-KPIs:** Quelle → Signavio Process Insights → SAC (Jira/ServiceNow als Signavio-Quellsysteme bereits vorhanden, KPI-Pakete konsumierbar)

---

### Interne Freigaben/Restriktionen

Im EKG keine policy-spezifische Whitelist gefunden. In der Praxis gelten:
- BDC-Kernbausteine (Datasphere, SAC, Signavio): üblicherweise unkritisch
- Non-SAP-SaaS-Quellen: Security/Compliance-Freigabe nötig (OAuth, Datenklassifizierung, Datenresidenz, Mandantenschutz)

→ Konkrete Freigabeliste für Signavio Engineering: bei Janine/Svitlana erfragen

---

### Referenzprojekte Engineering-KPIs (nicht ERP)

Im EKG keine ausgewiesenen Referenzprojekte für BDC + Engineering-KPIs gefunden. Engineering-/DevOps-KPI-Hubs (DORA, Ticket-, Build-KPIs) sind oft kundenspezifisch und selten als veröffentlichte Referenz geführt.

→ SAP-interne Referenzprojekte: bei Janine/Oliver anfragen (steht noch aus)

---

## EKX (Enterprise Knowledge Exploration) — Tool-Kandidat für KPI Hub

> Quelle: Janine Steidelmüller (weitergeleitet, 21.04.2026) — explizit zur Bewertung für KPI Dashboard Hub vorgeschlagen.

EKX ist SAP-intern und basiert auf dem **Enterprise Knowledge Graph (EKG)**. Spring Release (April 2026) erweitert EKX von reiner Wissensexploration zu einer "Creation Engine": Generierung von Dashboards, Diagrammen, PowerPoints, Websites, Code — alles geerdet in SAP-Inhalten.

**Einordnung für die Arbeit:**
- Kein klassisches KPI-Persistenz- oder Visualisierungstool (kein Datasphere/SAC-Ersatz)
- Potenziell relevant als **Erstellungs-/Deliverable-Layer** on top der KPI-Datenbasis
- Zu klären: Kann EKX live auf KPI-Datenquellen zugreifen, oder nur auf statische SAP-Inhalte?
- → Bewertung in Kap. 6 (Lösungsraum) als eigenständiger Kandidat oder Ergänzung zum BDC-Stack

---

## Weitere Tool-Kandidaten (EKG-Recherche, 21.04.2026)

### Integration & Datenzufuhr

- **SAP Integration Suite (Open Connectors / Cloud Integration):** Standardisierte Adapter für Non-SAP-Quellen (Jira, ServiceNow, Gainsight, CircleCI) via REST, Webhooks, Files. Im EKG Signavio-Bezug belegt. → Primärer Ingestion-Pfad für Non-SAP-Quellen.
- **SAP Business Accelerator Hub:** API-/Integrationsartefakte und Referenzbeispiele für schnelleren Aufbau von Ingestion-Flows.

### Experience-/Portal-Layer

- **SAP Build Work Zone:** Zentrales Portal ("Single Pane of Glass") zur Einbettung von SAC-Stories, Signavio-Kacheln, Dokumentation. Technisch naheliegend, kein expliziter Signavio-Engineering-KPI-Hub-Beleg im EKG.
- **SAP Mobile Start:** Mobile Exponierung von SAC-KPI-Kacheln (relevant falls Mobile-First für Leadership).

### IT-Ops / Projekt-KPIs

- **SAP Cloud ALM:** Betriebs- und Projekt-/Test-KPIs (Incidents, Deployments, Test Coverage). Im EKG explizit mit Signavio integriert belegt. → Als Datenquelle für Operations-KPIs einsetzbar.
- **SAP Solution Manager — Focused Insights:** Vorkonfigurierte IT-Betriebs-Dashboards (nur relevant falls SolMan noch aktiv).
- **LeanIX:** IT-Portfolio-/Architektur-KPIs; Einbettung in SAC/Work Zone als Kontextebene (Ownership, Lifecycle).

### Ergänzende Datenschicht

- **SAP HANA Cloud:** Für hochfrequente oder komplexe Berechnungen jenseits Datasphere-Standard; Near-Real-Time-Szenarien.

---

## Empfohlene Zielarchitektur (aus EKG-Recherche abgeleitet)

| Schicht | Tool(s) |
|---------|---------|
| Ingestion Non-SAP | Integration Suite (Open Connectors) + Signavio-Adapter (Jira/ServiceNow) |
| Persistenz/Semantik | SAP Datasphere |
| Prozess-/Service-KPIs | SAP Signavio Process Insights |
| Ops-/Projekt-KPIs | SAP Cloud ALM → Datasphere |
| Visualisierung/Monitoring | SAP Analytics Cloud (Stories, My Metrics, Alerts) |
| Portal/Experience | SAP Build Work Zone |
| Creation/Deliverables | EKX |
| Mobile | SAP Mobile Start (optional) |

---

## Svitlana-Meeting (22.04.2026) — Neue Erkenntnisse

- **SAC Data Steer** (via BDC → SAC): neuer Tool-Kandidat, näher ansehen
- **Collibra Data Intelligence Platform:** Landing Page ansehen — externer Kandidat
- **BDC Adoption Program (SharePoint):** "your golden ticket" laut Svitlana — unbedingt durcharbeiten
- **EKX:** Svitlana kennt es nicht, keine BDC-Projekte damit bekannt
- **Referenzprojekte:** Svitlana kennt keine für Engineering-KPIs
- **Präsentation:** Svitlana schickt noch nach → ✅ erhalten und ausgewertet (siehe unten)

---

## Svitlana-Präsentation: "Introducing BDC" (05.02.2026) — Auswertung

> Quelle: Svitlana Vlasova, "Introducing BDC: From Shopping in Collibra to Modelling in SAP DSP and Analytics in SAC", 05.02.2026. INTERNAL — SAP Only.

### BDC-Architektur (offiziell)

Der BDC-Stack besteht aus drei Kernkomponenten + Collibra als Governance-Layer:

| Komponente | Rolle |
|---|---|
| **SAP Analytics Cloud (SAC)** | Dashboards, Reporting, Planung — Consumption Layer |
| **SAP Datasphere (DSP)** | Datenintegration, Modellierung, Semantik — zentrale Datenschicht |
| **SAP Databricks** | AI/ML, Advanced Data Engineering (optional) |
| **Collibra** | Data Governance, Data Catalog, Lineage, Qualität, Privacy — **kein SAP-Produkt, aber fester Bestandteil des BDC-Stacks** |

**Wichtig:** Collibra ist nicht nur ein externer Kandidat — es ist die offizielle Governance-Plattform im BDC-Stack. Data Products werden über Collibra entdeckt, beantragt und governed.

### Data Products — Konzept

- Standardisierte, wiederverwendbare "business-ready" Datenassets
- Werden in Collibra katalogisiert (Suche, Metadata, Lineage, Ownership, SLAs)
- Lifecycle: Ideate → Initiate → Build & Govern → Publish → Consume → Maintain → Retire
- Beispiel-Use-Case: "BDC Operations Insights — Goals Tracking" (Product Satisfaction, Active Users, Cloud Availability, etc.)

### Datasphere 3-Schichten-Architektur

| Schicht | Zweck |
|---|---|
| **1 — Input Layer** | Rohdaten 1:1 aus Quellsystem, persistiert |
| **2 — Transformation Layer** | Business Logic: Joins, Unions, Aggregation, Harmonisierung → FACT Views |
| **3 — Output Layer** | Business-ready: Measures, Keys, Hierarchien, Analytic Models → SAC-Consumption |

### Datenfluss (End-to-End)

Quellsystem → Datasphere (Input → Transformation → Output) → Analytic Model → SAC (Live Connection → Story)

Auch möglich: Excel-Upload via CSV in Datasphere (für KPIs die noch nicht systemintegriert sind).

### BDC Adoption Program

- SAP nutzt BDC intern als "Customer Zero" — interne Strategie trifft externes Produkt
- **BDC Adoption Program:** Mentoring-Programm für Citizen User Adoption
- Svitlanas Use Case: "BDC&I Goals Tracking" — sie hat Platform Mentors (Gregory, Claudia)
- Spaces in Datasphere: "Goals Tracking", "BDD Goals Tracking Foundation", "General Manager 360"

### Relevante Personen (aus Präsentation)

- **Gregory Rohloff** — Data Product Owner (Goals Tracking)
- **Natasa Nakic** — Data Product Owner
- **Svitlana Vlasova** — Data Product Owner
- **Vikrant Shinde** — Data Product Owner

### Wichtige Links (aus Folie 8)

- BDC Adoption Program (SharePoint)
- Collibra Landing Page
- Initiate Data Product (Collibra)
- Request SAP Datasphere Space in Data for All Hub
- Mandatory Concepts (DSP-Modellierung)
- Use Case "Goals Tracking": Data Product + Foundation in Collibra

---

## Mural-Overview: Bestehende Dashboards & Links (22.04.2026, Oliver Timm)

> Quelle: Mural-Board, gemeinsam mit Oliver bis Freitag (24.04.) durcharbeiten. **Oberste Priorität.**

### Bereich: Product

**SharePoints:**
- Signavio PPR
- Signavio Product Excellence Dashboard
- Business Data Cloud

**SAC-Dashboards:**
- Signavio Product Excellence Dashboard
- Signavio Customer Reported Incidents & Bugs
- Adoption Monitor 2.0
- SAP Usage Analyser
- Consumed Annual Contract Value (CACV) Dashboard
- CACV Single Customer Analysis
- Product 360
- Operational Status Dashboard
- Signavio Dashboards
- Product Standard Requirements P&E
- Product Standard Compliance Dashboard
- Corporate Requirements Dashboard
- EVM - Infrastructure Vulnerabilities
- Cloud Health & Reliability Dashboard

**Collibra:**
- Product Experience Analytics Foundation

**Gainsight:**
- Signavio Dashboards

**Grafana:**
- SAP Signavio Release Management Security

**SAP Jira:**
- Jira Tools (Link)
- CPA Planning & Adoption Insights

**SAP Wiki:**
- Security Validations
- Rolling Calendar View cross initiatives

### Bereich: Security (aus Anastasia Zinkina Mails, März 2026)

> Quelle: E-Mail-Thread Anastasia Zinkina → Oliver Timm (04.–09.03.2026). Ansprechpartner Security-Dashboards: Anastasia Zinkina, Prashant Manerikar, Apoorva Veluvali. Zugang teils eingeschränkt (CAM-Profil, Sirius-Programm, Slack #data-insights-team).

**Security-Dashboard (Haupt-Dashboard):**
- Zugang über CAM-Profil beantragen
- Dokumentation vorhanden

**Incidents / Operational Status Dashboard:**
- Dokumentation: SAP Wiki (Signavio Data Insights)
- Dashboard in SAC
- Zugang via Slack #data-insights-team oder datainsights.signavio@groups.sap.com

**Hacker Simulation Findings:**
- Eingeschränkter Zugang (nur bei Findings im eigenen Team)
- Dashboard + Dokumentation im SAP Wiki (SIGSEC)

**Security Validation Findings:**
- Zugang nur für Sirius-Programm-Mitglieder
- Dashboard + Dokumentation im SAP Wiki (SIGSEC / SecVal)

---

### Bereich: Portfolio

**SAC-Dashboards:**
- E2E Portfolio Planning Dashboard
- E2E Portfolio QBR Dashboard

### Bereich: HR

*(noch keine Inhalte im Mural)*

---

## Kritischer Fit-Check für Signavio Engineering

BDC ist primär für ERP/S/4HANA konzipiert; Signavio-Engineering-Quellsysteme sind dominant Non-SAP. Kein "Plug-and-play" — Integrationsaufwand für REST-API-Ingestion ist real. Dies ist ein zentrales **Machbarkeitskriterium** für das Scoring-Modell (Kap. 7) und ein "erschwerender Faktor im konkreten Einsatzfall" i.S. Sachses Erwartungen.
