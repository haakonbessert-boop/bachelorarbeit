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

## Pendo Analytics (Oliver Timm, 23.04.2026)

> Quelle: "Pendo Analytics Playbook" — von Oliver Timm erhalten, 23.04.2026. SAP-internes Dokument.
> Relevant für Kap. 4 (Quellsystem Usage/Adoption), Kap. 6 (Tool-Kandidat), Kap. 7 (Scoring)

### Einordnung

Pendo ist ein **Product Analytics Tool**, das Nutzerverhalten in der Anwendung trackt (Feature-Clicks, Page Views, Sitzungsdauer). SAP nutzt Pendo intern — die Formulierung "SAP teams can utilise" und der direkte Playbook-Versand durch Oliver bestätigen eine aktive SAP-Lizenz.

**Wahrscheinliche Verbindung:** Die HEART-Metriken im Product Excellence Portal (DAU/MAU, Activated Users, Feature Adoption) und der "Adoption Monitor 2.0" sind mit hoher Wahrscheinlichkeit Pendo-Daten, die via SAC visualisiert werden.

### KPI-Abdeckung (Pendo nativ)

| Kategorie | KPIs |
|---|---|
| **Nutzungsintensität** | DAU, WAU, MAU, Visitor Count, Session Count |
| **Feature-Adoption** | Adoption Rate (% Nutzer die Feature nutzen), Top 5% Features by Clicks |
| **Retention / Stickiness** | Cohort Retention over Time, Feature-Stickiness |
| **Engagement-Score** | PES (Product Engagement Score) = Adoption + Stickiness + Growth |
| **Funnels** | Step-by-Step Konversionsraten in Key Flows |
| **Paths** | Navigationssequenzen vor/nach einer Aktion |
| **Segmentierung** | Nach Rolle, Plan, Region, Modul, Lifecycle Stage |

### Kernfunktionen (für KPI-Hub relevant)

- **Data Explorer:** Flexible Reports mit Filtern nach Segment, Feature, Zeitraum — inkl. Berechnungen (Sum, Ratio, Relative %)
- **Dashboards:** Role-specific Dashboards (Executive Readout, Feature Release Performance, Product Usage Overview, Roadmap Evidence)
- **Data Out:** Webhooks, REST API, Data Sync → direkte Integration in BI-Tools / CRM / Automation
- **Account Reports:** Aggregation auf Kundenkonto-Ebene (wichtig: zeigt Nutzung pro Account)

### Relevanz für KPI-Hub

| Aspekt | Bewertung |
|---|---|
| **Als Quellsystem** | Hoch — einzige belastbare Quelle für Feature-Adoption und DAU/WAU/MAU bei Signavio |
| **Als Tool-Kandidat (Kap. 6)** | Mittel — Pendo hat eigene Dashboards, aber kein Portal-Layer; Datenbasis stark, UX-Standalone begrenzt |
| **RBAC** | Pendo-Segmentierung erlaubt rollenbasierte Ansichten; Zugang noch zu klären |
| **Integration in BDC** | Über "Data Out" (API/Webhooks) → Datasphere → SAC theoretisch möglich |

### Offene Fragen

- Wer hat Pendo-Admin-Zugang? (Janine/Oliver fragen)
- Ist der Adoption Monitor 2.0 ein Pendo-Dashboard in SAC oder natives Pendo?
- Kann Pendo-Daten direkt in Datasphere repliziert werden (via Data Sync)?

---

## Mural-Dashboard-Analyse (23.04.2026)

> Quelle: Mural-Board Oliver Timm — systematische Durchsicht aller ~25 Links am 23.04.2026.
> Mural-Struktur: **Product**, **Operations**, **HR** (leer)

### Legende

| Symbol | Bedeutung |
|--------|-----------|
| ✅ | Zugang vorhanden, Daten sichtbar |
| ⚠️ | Partieller Zugang oder Datenproblem |
| ❌ | Kein Zugang / defekter Link |

---

### Bereich: Product

#### SAC-Dashboards (Signavio-spezifisch — hohe Relevanz)

**Operational Status Dashboard** ✅
- Signavio-eigenes Dashboard (2 Seiten)
- **KPIs:** MTTR (Service Degradation + Disruption in h), Incidents/Monat (High/Medium/Low/No Impact/Internal), MTTR per Product Area (FIT, MxG, PAM, CloudOS), Security Incidents; Seite 2: Drilldown-Tabelle aller High/Medium-Tickets mit TTR
- **Quellsystem:** ServiceNow (Ticket-IDs: SIGINCIDENT-XXXX bestätigt)
- **Filter:** Incident Key, Region, Risk Impact Class, Product Area, Classification
- Daten aktuell (bis Apr 2026)
- **Relevanz:** Hoch — KPI-Kategorie "Operational Health"
- Auffällig: SIGINCIDENT-1175 mit 84h 50m TTR (MxG); PAM dominiert Incident-Volumen

**Signavio Customer Reported Incidents & Bugs — Quarterly View** ⚠️
- Signavio-eigenes Dashboard (3 Seiten)
- **KPIs:** Total Bugs (142, +3% QoQ), Avg. Bug Resolution (30 Tage), Avg. Incident Resolution (23 Tage), Bugs per Priority, Resolution Categories, Product Bugs Share/Quarter, Top 10 Customers, Top 10 Components
- Quellsystem: Jira/Kundenmeldungen
- **Problem:** Updated Aug 22, 2025 — Daten 8 Monate alt; nur bis Q2 2025
- **Relevanz:** Hoch — KPI-Kategorie "Support/Quality"; aber Freshness-Problem
- Auffällig: 40 Bugs >4 Wochen offen; Access Management SAP Signavio häufigste Komponente (185)
- Hinweis: 142 Bugs = identische Zahl wie im HEART Quarterly — gleiche Datenquelle

**Signavio Dashboards (SAC-Ordner)** ✅ (Navigation)
- SAC File Browser / Container-Ordner mit Unterordnern und Stories
- Enthält: Content Dashboards, Jira Dashboards, License and Feature, Product Usage Dashboards, VAD - Value Accelerator + 2 Stories
- Führt zu bereits bekannten Dashboards (u.a. Operational Status)
- **Kein eigenständiger Eintrag** — Navigation zu Sub-Dashboards
- Offene Frage an Oliver: Welche Unterordner sind Engineering-relevant?

#### SAC-Dashboards (Corporate — mittlere Relevanz)

**Cloud Health & Reliability Dashboard (2.0 CHR Summary)** ✅
- Corporate Processes & Information Technology
- **KPIs:** Cloud Operations (Avg Tenant Outage Min, Initial Cust. Comm. in 15', SLA Violation %, % RCA Compl. in 10 Days) + Infrastructure (MTTR Infra, Avg Infra. Availability, Service Disruptions Count, % RCA Compl. in 8 Days) + Additional Facts YTD (SWAT Count, Total Downtime Min)
- Sichtbare Werte: SLA Violation **1,17%** (Ziel 0,5% — drüber), RCA Completion **87%** (Ziel 80% ✅), SWAT Count YTD: **10**, Infra. Availability Ziel: **99,90%**
- Filter: Solution Area, Dev Org (aktuell PE Ariba/Business — kein Signavio-Filter bestätigt)
- **Relevanz:** Hoch als Referenz; Signavio-Filter noch zu prüfen
- Relation zu Operational Status Dashboard: CHR = Corporate Cloud-Reliability-Layer; #11 = Signavio-spezifische Incident-Ebene

**Product Standard Requirements P&E** ✅
- Corporate Processes & Information Technology (9 Seiten)
- **KPIs:** PSR Compliance-Status (Fulfilled vs. non-compliant) nach Corporate/Mandatory/Integration/UX Consistency PSRs
- Quellsysteme: Sirius + HyCoM
- Cut-off: Apr 2026, 6-Monats-Fenster
- **Relevanz:** Mittel — KPI-Kategorie "Release Management / Product Standards"

**Corporate Requirements Dashboard (NEW)** ✅
- Corporate Processes & Information Technology (9 Seiten)
- **KPIs:** CR Violations (Non-Security + Security), Current Status, LoB Overview, Time Trend, Violation Early Warning, BuLi Tabelle
- **Relevanz:** Mittel — KPI-Kategorie "Corporate Requirements"; bildet Compliance-Cluster mit #13 und #14
- Hinweis: Cluster-Empfehlung — PSR (#13), Compliance (#14), Corporate Requirements (#15) als eine Integrationskategorie für den KPI-Hub

**Product Standard Compliance Dashboard** ⚠️
- Beim Durchgang nicht geladen — noch zu prüfen (vermutlich ähnlich wie #13)

**EVM — Infrastructure Vulnerabilities** ⚠️
- SGSC Dashboard (EVM LOB Report), 2 Seiten (EVM Drill Down + EVM Trends)
- **KPIs:** L1 Goal Compliance (90d): Vulnerability-SLA nach Severity (Emergency/Critical/High/Medium/Low), Open vs. Fixed, Open vs. Risk Accepted, SLA Compliance per L3/L4 Unit, Avg. Vulnerability Age
- Partieller Zugang — neue EVM-Rolle nötig (EA Store)
- **Relevanz:** Hoch — KPI-Kategorie "Release Management / Security Findings"
- **Aktion:** Neue EVM-Rolle über EA Store beantragen (Link war im Dashboard-Banner)

#### SAC-Dashboards (Corporate — geringe Relevanz)

**SAP Usage Analyzer | Product Factsheet** ❌ (SUNSET)
- **Abgekündigt** — "Please use the Detailed Product Analysis instead"
- **Aktion für Oliver:** Mural-Link auf Detailed Product Analysis aktualisieren

**SAP Usage Analyzer | Product Analysis (Detailed)** ✅
- Corporate Processes & Information Technology (7 Seiten: Overview, cACV, Solution Capabilities, Features, Solution Data Objects, Customers, Value Drivers)
- **KPIs:** MAU-Trend (~278k), Customer Count (Live/Project/Shelfware), Active Scope (76%), Measured Product Scope (85%), Avg. Functional Footprint, Upcoming Renewals
- Aktuell auf LPR243 (S/4HANA Finance Cloud) gefiltert — kein Signavio-Filter bestätigt
- **Relevanz:** Mittel — Usage/Adoption-KPIs; Signavio-LPR-Filter noch zu prüfen

**Consumed Annual Contract Value (CACV) Dashboard** ⚠️
- Corporate Processes & Information Technology
- **KPIs:** 2026 YTD cACV (mEUR), YTD cACV YoY Growth, BTP Monthly cACV Trendline
- Keine Daten sichtbar (auf BTP gefiltert, kein Signavio-Datensatz)
- **Relevanz:** Gering — GtM/Financials-Tool, kein Engineering-KPI

**CACV Single Customer Analysis** ⚠️
- Single-Customer Drilldown (aktuell Nestlé-Filter)
- Keine Signavio-relevanten Daten sichtbar
- **Relevanz:** Gering — GtM/Sales-Tool

**Product 360** ❌
- Global Adoption & Experience CoE (2 Seiten)
- **KPIs:** Customers, Usage (MAU, Active Scope), AI Usage (Base/Premium AI Features), PX (PSAT, Usefulness, Ease of Use), Commercials (Cloud Revenue, Backlog, Bookings, Pipeline), Support (Call Rate, Avg Days to Solve, Customer Effort Score)
- Kein Zugang — Authorization via EA Store (48h Wartezeit)
- **Relevanz:** Hoch als Referenz — konzeptionell der KPI-Hub für Product-KPIs; fehlt: Engineering/DORA-KPIs
- **Aktion:** EA Store Access beantragen — jetzt, damit innerhalb 48h verfügbar

**Adoption Monitor 2.0** ❌
- Kein Zugang — Berechtigungen fehlen
- Frage an Janine: Wie beantragen?

#### Collibra

**Product Experience Analytics Foundation** ✅
- Collibra — Data for All Hub (SAP / 01-Product Development)
- **Typ:** Data Product (Derived, Gold-Qualität) — keine Dashboard-Ansicht, sondern Datenbasis
- **Inhalt:** Qualtrics PX Survey-Daten + Mapping zu LPR, Solution Areas, Tenants, Customers
- SAP Datasphere Ready ✅, SAP Analytics Cloud Ready ✅, Architecture Execution CoE approved ✅
- Status: Published, fixer Scope
- **Relevanz:** Mittel — Datenquelle für PX/PSAT-KPIs; zeigt BDC-Stack-Funktionsweise in der Praxis (Collibra → Datasphere → SAC)

#### Gainsight

**Signavio Dashboards (Gainsight)** ❌
- Kein Zugang — Zugangsdaten bei Janine erfragen

#### Grafana

**SAP Signavio Release Management Security** ❌
- Kein Zugang — Zugangsdaten bei Janine erfragen

#### SAP Jira

**Signavio Micro Deliveries** ✅
- SAP Jira — Signavio-spezifisch
- **KPIs:** Management Status RAG (361 GREEN, 0 RED/YELLOW), Progress of MD (55% Done, 695 Issues), Documentation Status (74% Done), X-Ray Status per Sub-Group, In Pre-Release Delivery Group Split, Product Board Info per Group (FIT/MXG/PA&M/NEXT)
- Sub-Groups: Platform Services, Process.AI, Transformation Enablement, SPG, M&C, Connectivity, Suite Essentials
- Filter: Current MD, Version/Delivery, Status, Assignee, Team, Labels, Sub-Groups, JQL
- ⚠️ Performance Notice aktiv ("bulk operations may be slow")
- **Relevanz:** Hoch — KPI-Kategorie "Delivery / Release Management"; RAG-Status exakt das Signal das der KPI-Hub surfacen soll
- Hinweis: Performance-Banner = direkter Beleg für "Poor performance"-Stakeholder-Complaint aus REQUIREMENTS.md

**CPA Planning & Adoption Insights (Semester Plan Cross Topic)** ✅
- SAP Jira (jira.tools.sap) — SAP-weit
- **KPIs:** Adoption Status (Open: 3.195 / In Progress: 733 / Done: 2.702 / Blocked: 144), Planning Status (Unplanned: 29%, Done: 28%, Exception Approved: 24%)
- 9.586 Issues gesamt — BTP, AI, Ariba, Business Networks
- **Relevanz:** Gering — SAP-weit, nicht Signavio Engineering-spezifisch

#### SAP Wiki

**Rolling Calendar of Cross Initiatives** ✅
- Wiki@SAP — erstellt von Anna Maria Muhs, zuletzt Apr 08, 2026
- **Typ:** Statische Transparenzschicht — kein Dashboard, keine KPI-Daten
- Zeigt alle cross-team Initiativen in P&E (Was/Wann/Für wen/Abhängigkeiten)
- Migration zu ProductBoard geplant
- **Relevanz für KPI-Hub:** Mittel als Kontext — zeigt Initiativen die Datenquellen betreffen
- Thesis-relevante Initiativen: Unified Metering (non-billable usage, Owner: Kuchenbecker/Muhs), Hyperspace/Circle CI Migration (Owner: Beppler Christopher), HAIM (Auth/RBAC), Data & Analytics Initiative (Owner: Barbara Schories)
- FAQ-Zitat für Kap. 4: *"If BDC integration is prioritized... PA&M and MxG would add the relevant data-product deliveries in NEXT"*

#### Product Excellence Portal (SAP Signavio)

**SAP Signavio Product Excellence Dashboards Portal** ✅
- Signavio-eigenes Portal mit 4 Kategorien: HEART, Revenue Insights, Product Management, Customer Insights
- HEART-Substruktur: Quarterly View / Half-Annual View / Annual View (jeweils eigene Dashboards)
- **KPIs sichtbar (HEART Quarterly Q2/2025):** PSAT 100%, DAU/MAU 10%, Added Content 5,4 Mio., Terminated Value 5.050 Tsd.€, Customer Reported Bugs 142, Added ACV Bookings 24,1 Mio.€, MAU 76,2 Tsd., Activated Users 1.392 Tsd.
- ⚠️ HEART-Dashboard deprecated: *"Due to deprecating classic SAC Stories this Dashboard is no longer supported. Please Use 'Quarterly Products HEART Dashboard Optimized Design Experience'"*
- ⚠️ Daten veraltet: Updated Apr 25, 2025 — Daten bis Q2 2025 (8 Monate alt)
- **Relevanz:** Sehr hoch als Referenz — **einziger existierender Signavio Portal-Ansatz**
- Kritischer Befund: Deckt nur Product-KPIs ab (HEART, Revenue, Customer) — Engineering-KPIs (DORA, Delivery, Ops) fehlen komplett
- Architekturelle Frage für Kap. 6: Erweiterung dieses Portals oder eigenständige Lösung?
- Navigation-Problem: 3-Ebenen-Struktur (Portal → Kategorie → Kadenz → Dashboard) — widerspricht "Where do I find what?"-Anforderung

---

### Bereich: Operations

**E2E Portfolio Planning Dashboard (SAC)** ❌
- Link defekt — "Diese Datei konnte nicht gefunden werden"
- Frage an Oliver: Existiert noch? Wer ist Owner?

**E2E Portfolio QBR Dashboard (SAC)** ❌
- Link defekt — "Diese Datei konnte nicht gefunden werden"
- Frage an Oliver: Existiert noch? Wer ist Owner?

---

### Bereich: HR

*(Keine Inhalte im Mural)*

---

### Gesamtfazit Mural-Analyse

#### Zahlen
Von ~25 Links: **~8 vollständig zugänglich mit Daten**, ~8 kein Zugang, ~3 deprecated/veraltet, ~2 defekte Links.

#### Kernbefunde

| # | Befund | Thesis-Relevanz |
|---|--------|----------------|
| 1 | **Fragmentierung messbar:** 7 verschiedene Systeme, kein einheitlicher Einstieg | Kap. 1 + 4 |
| 2 | **RBAC-Problem real:** Fast jedes 3. Dashboard nicht zugänglich (CAM, EA Store, Sirius) | Kap. 4 + 5 |
| 3 | **DORA-Metriken fehlen komplett** — kein einziges Dashboard für Deployment Frequency, Lead Time, etc. | Kap. 4 + 5 (Lücke) |
| 4 | **Datenfreshness-Problem:** HEART veraltet (8 Monate), Bugs-Dashboard (8 Monate), deprecated Komponenten | Kap. 4 |
| 5 | **Stärkste Dashboards:** Operational Status (#11, ServiceNow) + Jira Micro Deliveries (#21) | Kap. 4 + 8 (MVP-Quellen) |
| 6 | **Product Excellence Portal = Präzedenzfall:** Portallösung existiert für Product-KPIs — Engineering fehlt | Kap. 6 |

#### KPI-Abdeckung (Ist-Zustand)

| KPI-Kategorie (aus OneDashboard) | Abdeckung | Dashboard |
|---|---|---|
| Operational Health (Incidents, SLA, MTTR) | ✅ Gut | Operational Status Dashboard |
| Delivery / DORA | ⚠️ Partiell (Jira) | Micro Deliveries (kein DORA) |
| Release Mgmt / Compliance | ✅ Vorhanden | PSR, Corporate Requirements, EVM |
| Usage / Adoption | ⚠️ Lücke | Usage Analyzer (kein Signavio-Filter), Gainsight (kein Zugang) |
| HEART / PX | ⚠️ Veraltet | Product Excellence Portal (deprecated) |
| Financials / GTM | ❌ Kein Zugang | CACV (kein Datensatz), Product 360 (kein Zugang) |
| People / HR | ❌ Leer | — |
| DORA-Metriken | ❌ Fehlt | — |

#### Offene Aktionen

| Priorität | Aktion | An wen |
|---|---|---|
| Heute | EA Store: Product 360 Access beantragen | Selbst |
| Heute | EA Store: EVM neue Rolle beantragen | Selbst |
| Freitag | Gainsight Zugangsdaten | Janine |
| Freitag | Grafana Zugangsdaten | Janine |
| Freitag | Adoption Monitor 2.0 Zugang | Janine |
| Freitag | Operations Links (E2E Portfolio): Owner + Status | Janine/Oliver |
| Freitag | Mural-Link Usage Analyzer aktualisieren | Oliver |
| Freitag | SAP Usage Analyzer + CHR: Signavio-Filter vorhanden? | Janine |
| Nächste Woche | DORA-Metriken: Gibt es ein Dashboard dafür? | Oliver |
| Nächste Woche | SAP_Signavio_Dashboards Unterordner (Jira, Product Usage) | Oliver |

---

## #OneDashboard Vision-Dokument (Oliver Timm)

> Quelle: "one-signavio-metrics-dashboard.pdf" — Oliver Timm. Beschreibt die übergreifende #OneDashboard-Initiative mit KPI-Kategorien, bestehenden Initiativen, Hindernissen und Next Steps.

### Vision

"We have #OneDashboard with all relevant KPIs visualized in various categories that everyone can consider while deciding."

Aktuell: monatlicher KPI-Report als PDF (Fokus: Headcount, Financials, Release Management). Mehrere parallele Initiativen, keine Harmonisierung.

### KPI-Kategorien (vollständig)

**GTM KPIs:**
- Renewal Rate FC/ACT, Net Retention Rate, Licensed Customers, Health Score (CSP Managed)

**Service KPIs:**
- Value of Services Sold (Volume, Net Value, Backlog), Avg. PD/Service, Win Rate, Customer Satisfaction Score, Utilization (Billable/Chargeable/Investment), Services Bookings Value (Pipeline), Service to License Attach Rate, Churn/Renewal Rate (Service Attached), Profitability of Services

**People KPIs:**
- P Actuals (FTE/Heads), HC/NHC/Maternity, Terminations, Starters, Diversity (Gender, Early Talent, Females in Management), Career Level (T-Level), Job Function/Group/Title, Org Unit/Cost Center, Location Strategy (Low/Mid/High Cost), Attrition Rate

**Usage:**
- Software- und Feature-Nutzung (nicht weiter spezifiziert)

**Delivery (DORA + Jira):**
- Deployment Frequency, Lead Time for Changes, Change Failure Rate, Time to Restore Service, Throughput, Cycle Time, (Velocity)

**Release Management:**
- Total Non-assessed Vulnerabilities, Product Standards Compliance (Corporate, Top-X, Accessibility, Integration), Key Customer Issues / Operational Events / Outages

**Financials:**
- P&L Statement, Actuals, Budget, Forecast

### Bestehende Initiativen (Stand des Dokuments)

| Initiative | Owner | Status | Beschreibung |
|---|---|---|---|
| **COO Cross Team** | Jens Hildenbrand | **On Hold** (wegen Re-Org) | SAP Signavio Dashboard / Digital Boardroom für Rouven, Gero und LT. Standard-KPIs via ID&A + Signavio-spezifische KPIs. Alle Units hatten Unit-spezifische KPIs beigesteuert |
| **GTM** | Julius Meinl | Laufend | E2E Steering Model für G2M. High-level Health Overview für Senior Management |
| **Process Intelligence** | Björn Wagner, Rohini Geetha Soman Nair | Laufend | JIRA-Daten (Release Prediction), Usage Data mit Event Logs |
| **DORA & QA Metrics** | Stefan Popescu et al. | OKR, nicht voll besetzt | DORA & QA Metrics Dashboard |
| **Process Insights** | — | Produktiv | 3 Cloud Reporting Dashboards: SAP Signavio Ops, SAP Process Insights, Solution Area – SAP Signavio |
| **PM&Strategy** | — | Migration geplant | "Data-Driven Product Management Initiative", aktuell on-prem Tableau, Migration zu SAC geplant |

### Hindernisse (aus Dokument)

1. **Verschiedene Datenquellen** → Integration komplex
2. **Zu viel manueller Aufwand** → Aggregation und Visualisierung händisch
3. **Access Rights** → Units haben unterschiedliche Zugriffsrechte → Policy/Procedures nötig
4. **Nicht genug Kapazität** → COO-Office hat nicht genug Ressourcen
5. **Kein klares Ownership** → Keine dedizierte Verantwortung, andere SAP-Units allokieren mehrere FTEs

### Next Steps (aus Dokument)

1. LT-Mandat einholen für zentrale Initiative
2. Plan erstellen: wie soll Dashboard aussehen, Alignment mit allen Initiative-Owners
3. Plan dem Management präsentieren, Kapazitäten klären
4. Mit Julius (GTM) auf Product-KPIs aus CS alignen

---

## Kritischer Fit-Check für Signavio Engineering

BDC ist primär für ERP/S/4HANA konzipiert; Signavio-Engineering-Quellsysteme sind dominant Non-SAP. Kein "Plug-and-play" — Integrationsaufwand für REST-API-Ingestion ist real. Dies ist ein zentrales **Machbarkeitskriterium** für das Scoring-Modell (Kap. 7) und ein "erschwerender Faktor im konkreten Einsatzfall" i.S. Sachses Erwartungen.
