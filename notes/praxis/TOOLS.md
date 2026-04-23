# Tools & Systemlandschaft — Praxisphase SAP Signavio

Forschungskontext: KPI-Hub für SAP Signavio Engineering — Mehrkriterien-Entscheidungsmodell.
Kapitelzuordnung: **A–C → Kap. 4 (Ist-Zustand)** | **D–E → Kap. 6 (Lösungsraum)** | **F → Kap. 7 (Scoring/Fit-Check)**

Quellsysteme (Anforderungsseite) → ergänzend [REQUIREMENTS.md](../REQUIREMENTS.md).

---

## A — Quellsysteme: Ist-Zustand

### A.1 Master-Übersicht

| Quellsystem | KPI-Kategorien | Zugang | Datenfrische | Integrationsweg |
|---|---|---|---|---|
| **ServiceNow** | Incidents, MTTR, SLA, TTR | ✅ via SAC-Dashboard | Aktuell (Apr 2026) | Signavio-Adapter (produktiv) |
| **Jira (SAP Jira)** | Delivery-Status, RAG, Issues, Bugs | ✅ direkt | Aktuell | Signavio-Adapter (produktiv) |
| **Pendo / Data Insights DB** | DAU/WAU/MAU, Feature Adoption, Retention, PES | ❌ kein Admin-Zugang | Unklar | REST API / Data Sync |
| **Qualtrics** | PSAT, PX Survey | ❌ kein Direktzugang | Manueller Export | REST API möglich |
| **Gainsight** | Customer Health Score, CS-KPIs, Churn | ❌ kein Zugang | Unklar | REST API |
| **Grafana** | Release Mgmt Security | ❌ kein Zugang | Realtime | REST API / Export |
| **CircleCI** | Build/Deploy-KPIs (DORA-Quellen) | ❌ nicht im Mural | Realtime | REST API |
| **SAC Analytics Store** | Financials, ACV, Bookings, Revenue | ⚠️ nur Corporate-Filter | Aktuell | SAC nativ |
| **Sirius / HyCoM** | PSR Compliance-Status | ⚠️ via SAC-Dashboard | Apr 2026 | SAC nativ |
| **Cloud Reporting** | Customer License data | ⚠️ Corporate-Filter | Unklar | SAC nativ |
| **SAP Cloud ALM** | IT-Ops: Incidents, Deployments, Test Coverage | ⚠️ EKG-Beleg vorhanden | Unklar | Datasphere → SAC |
| **Collibra (PX Foundation)** | Qualtrics-Survey-Daten, LPR-Mapping | ✅ als Data Product | Gold-Qualität | Datasphere Ready |

> **DORA-Lücke:** Kein einziges Quellsystem liefert aktuell vollständige DORA-Metriken. Deployment Frequency, Lead Time, CFR, MTTR (als DORA) wären primär in CircleCI — Zugang ungeklärt. DORA-Initiative bei Stefan Popescu existiert als OKR, ist aber nicht voll besetzt.

### A.2 Quellsystem-Details

#### Pendo Analytics / „Data Insights Database"

> Quelle: Pendo Analytics Playbook — von Oliver Timm erhalten, 23.04.2026.

Pendo ist ein **Product Analytics Tool**, das Nutzerverhalten in der Anwendung trackt. SAP nutzt Pendo intern (aktive Lizenz durch Oliver-Playbook bestätigt). Intern wird Pendo-Data über die **„Data Insights Database"** aggregiert und von dort in SAC visualisiert (DAU/MAU → Pendo → Data Insights DB → SAC).

**Wahrscheinliche Verbindung:** Die HEART-Metriken im Product Excellence Portal (DAU/MAU, Activated Users, Feature Adoption) und der „Adoption Monitor 2.0" sind mit hoher Wahrscheinlichkeit Pendo-Daten.

| KPI-Kategorie | KPIs |
|---|---|
| Nutzungsintensität | DAU, WAU, MAU, Visitor Count, Session Count |
| Feature-Adoption | Adoption Rate (% Nutzer die Feature nutzen), Top 5% Features by Clicks |
| Retention / Stickiness | Cohort Retention over Time, Feature-Stickiness |
| Engagement-Score | PES (Product Engagement Score) = Adoption + Stickiness + Growth |
| Funnels | Step-by-Step Konversionsraten in Key Flows |
| Paths | Navigationssequenzen vor/nach einer Aktion |
| Segmentierung | Nach Rolle, Plan, Region, Modul, Lifecycle Stage |

**Offene Fragen:** Wer hat Pendo-Admin-Zugang? Ist Adoption Monitor 2.0 ein Pendo-Dashboard in SAC oder natives Pendo? Kann Pendo-Data via Data Sync in Datasphere repliziert werden?

#### Qualtrics

Quelle für PSAT- und PX-Survey-Daten. Bisher manueller Export in PPR-Prozess (laut One Voice Alignment Sheet, Q3 Data Availability Table). API-Integration für Near-Realtime möglich, aktuell nicht umgesetzt.

#### ServiceNow

Primäre Quelle für Incident-KPIs. Jira/ServiceNow sind als Quellsysteme in Signavio Process Insights produktiv eingebunden (Signavio-Adapter vorhanden). Bestätigt durch Operational Status Dashboard (SIGINCIDENT-Ticket-IDs sichtbar).

#### Jira (SAP Jira)

Primäre Quelle für Delivery- und Release-KPIs. Signavio-Adapter produktiv. Performance-Probleme bekannt (Performance Notice aktiv im Micro Deliveries Dashboard — direkter Beleg für Requirements-Complaint).

---

## B — Dashboard-Landschaft: Ist-Zustand

### B.1 Übersicht aller Mural-Dashboards (23.04.2026)

**Legende:** ✅ Zugang vorhanden | ⚠️ Partiell/Datenproblem | ❌ Kein Zugang / defekt

| Dashboard | System | KPI-Kategorie | Zugang | Frische | Relevanz |
|---|---|---|---|---|---|
| Operational Status Dashboard | SAC / ServiceNow | Operational Health | ✅ | Aktuell | **Hoch** |
| Customer Reported Incidents & Bugs | SAC / Jira | Support/Quality | ⚠️ | 8 Monate alt | **Hoch** (Freshness-Problem) |
| Cloud Health & Reliability (CHR) | SAC (Corporate) | Cloud-Ops | ✅ | Aktuell | **Hoch** (Signavio-Filter prüfen) |
| EVM — Infrastructure Vulnerabilities | SAC (SGSC) | Security | ⚠️ | Aktuell | **Hoch** (EA Store ausstehend) |
| Signavio Micro Deliveries | Jira | Delivery/Release | ✅ | Aktuell | **Hoch** |
| Product Excellence Portal (HEART) | SAC / Pendo | HEART/Revenue/PX | ⚠️ | 8 Monate alt | **Sehr hoch** (Präzedenzfall, veraltet) |
| Product 360 | SAC (CoE) | Product KPIs gesamt | ❌ | Aktuell? | **Hoch** als Referenz (EA Store ausstehend) |
| Adoption Monitor 2.0 | SAC / Pendo? | Usage/Adoption | ❌ | Unklar | **Hoch** (Pendo-Verbindung) |
| Signavio Dashboards (Gainsight) | Gainsight | CS/Customer Health | ❌ | Unklar | **Hoch** (kein Zugang) |
| Release Mgmt Security | Grafana | Security | ❌ | Realtime | **Hoch** (kein Zugang) |
| Product Standard Requirements P&E | SAC (Corporate) | PSR Compliance | ✅ | Apr 2026 | Mittel |
| Corporate Requirements Dashboard | SAC (Corporate) | Compliance | ✅ | Aktuell | Mittel |
| Product Standard Compliance | SAC (Corporate) | Compliance | ⚠️ | Unklar | Mittel |
| SAP Usage Analyzer (Detailed) | SAC (Corporate) | Usage/Adoption | ✅ | Aktuell | Mittel (kein Signavio-Filter) |
| Product Experience Analytics Foundation | Collibra | PX/PSAT-Datenbasis | ✅ | Gold | Mittel (Datenbasis, kein Dashboard) |
| Rolling Calendar of Cross Initiatives | Wiki | Initiativen-Kontext | ✅ | Apr 2026 | Mittel (kein KPI-Feed) |
| CPA Planning & Adoption Insights | Jira (SAP-weit) | Portfolio Planning | ✅ | Aktuell | Gering (nicht Signavio-spezifisch) |
| CACV Dashboard | SAC (Corporate) | Financials | ⚠️ | Aktuell | Gering (kein Signavio-Datensatz) |
| CACV Single Customer | SAC (Corporate) | Financials/Sales | ⚠️ | Aktuell | Gering |
| E2E Portfolio Planning | SAC | Operations | ❌ defekt | — | Unbekannt |
| E2E Portfolio QBR | SAC | Operations | ❌ defekt | — | Unbekannt |
| SAP Usage Analyzer (Factsheet) | SAC (Corporate) | — | ❌ SUNSET | — | Keiner (deprecated) |
| Signavio Dashboards (SAC-Ordner) | SAC | Navigation | ✅ | — | Kein Eigenwert |

### B.2 KPI-Abdeckungsmatrix (Ist-Zustand)

| KPI-Kategorie | Abdeckung | Bestes verfügbares Dashboard | Lücke / Problem |
|---|---|---|---|
| Operational Health (Incidents, SLA, MTTR) | ✅ Gut | Operational Status Dashboard | — |
| Delivery / Jira-KPIs | ✅ Gut | Micro Deliveries | Kein vollständiges DORA |
| **DORA-Metriken** (Deploy Freq., Lead Time, CFR) | **❌ Fehlt komplett** | — | Größte Lücke; CircleCI-Zugang ungeklärt |
| Compliance / PSR | ✅ Vorhanden | PSR, Corporate Requirements | EVM-Zugang ausstehend |
| Security / Vulnerabilities | ⚠️ Partiell | EVM (ausstehend), Grafana (kein Zugang) | Zugänge fehlen |
| Usage / Adoption (DAU/MAU) | ⚠️ Lücke | Usage Analyzer (kein Signavio-Filter) | Pendo-Direktzugang fehlt |
| HEART / PX / PSAT | ⚠️ Veraltet | Product Excellence Portal | 8 Monate alt, deprecated |
| Customer Health / Gainsight | ❌ Kein Zugang | Gainsight | Zugangsdaten fehlen |
| Financials / GTM | ❌ Kein Datensatz | CACV, Product 360 | CACV kein Signavio-Filter; Product 360 gesperrt |
| People / HR | ❌ Leer | — | Kein Mural-Inhalt |

### B.3 PPR — Aktueller Status quo (Ist-Zustand Reporting)

> Quelle: VoC „One Voice" Alignment Sheet, 05.11.2025 — Lea Reib, Oliver Timm, Janine Steidelmüller.

Das PPR (Product Performance Review) ist aktuell das einzige übergreifende Reporting-Instrument — ein **quartalsweiser PowerPoint-Report** des Product Excellence Teams.

| Kennzahl | Q2 2025 | Q3 2025 |
|---|---|---|
| Slides gesamt | 150 | 85 |
| davon Financials | ~50% | — |
| davon Pendo (Product Usage) | 6 | — |
| davon HEART | 5 | — |
| davon Quality (Customer Support) | 4 | — |
| **Aufwand Erstellung** | **5–10 Tage** | — |

Erstellungsaufwand-Schätzung: Janine: 5–10 Tage; Lea Reib: „1–2 Wochen inkl. Datenabfragen aus verschiedenen Teams."

**Kritische PPR-Probleme (direkt aus dem Dokument):**
- Keine Echtzeit-Daten — Daten 1+ Monat nach Quartalsende noch nicht vollständig
- Kein Kundenfilter / keine Customisierung möglich
- Resolution Time berechnet auf Created vs. Resolved (ignoriert kundenseitige Haltezeiten)
- Keine Differenzierung Bug / Incident / 1st-2nd-3rd-Level-Ticket
- Keine korrelierten Analysen (z.B. Bug-to-Incident-Ratio)
- Definitionen unterscheiden sich von internen Support-Ansichten

> **Thesis-Relevanz (Kap. 4):** Der PPR ist der quantifizierte Schmerzpunkt — 5–10 Tage manueller Aufwand für eine 150-Folien-Quartalsübersicht ist exakt das Problem, das der KPI-Hub lösen soll.

**Datenquellen hinter PPR / HEART (aus Q3 Datenverfügbarkeitstabelle):**

| KPI | HEART-Kategorie | Quelle |
|---|---|---|
| DAU & MAU | Adoption | **Data Insights database** (= Pendo-Aggregat) |
| Activated Unique Users | Adoption | **Data Insights database** |
| Product Content Data | Task Success | **Data Insights database** |
| Customer License data | — | Cloud Reporting |
| Survey data (PX / PSAT) | Happiness | **Qualtrics Export** (manuell) |
| Customer reported bugs | Quality | **ServiceNow** |
| Contract Terminations / Win-Loss / ACV | — | **SAC Analytics Store** |

### B.4 Dashboard-Details

#### Operational Status Dashboard ✅

- Signavio-eigenes Dashboard (2 Seiten), Quellsystem: ServiceNow
- **Seite 1 — KPIs:** MTTR Service Degradation (h), MTTR Service Disruption (h), Incidents/Monat nach Impact-Klasse (High/Medium/Low/No Impact/Internal), MTTR per Product Area (FIT, MxG, PAM, CloudOS), Security Incidents
- **Seite 2:** Drilldown-Tabelle aller High/Medium-Tickets mit individuellem TTR
- Filter: Incident Key, Region, Risk Impact Class, Product Area, Classification
- Daten aktuell (bis Apr 2026). Auffällig: SIGINCIDENT-1175 mit 84h 50m TTR (MxG); PAM dominiert Incident-Volumen
- **Thesis-Relevanz:** Hoch — stärkste verfügbare Quelle für Operational Health KPIs; MVP-Kandidat

#### Customer Reported Incidents & Bugs — Quarterly View ⚠️

- Signavio-eigenes Dashboard (3 Seiten), Quellsystem: Jira / Kundenmeldungen
- **KPIs:** Total Bugs (142, +3% QoQ), Avg. Bug Resolution (30 Tage), Avg. Incident Resolution (23 Tage), Bugs per Priority, Resolution Categories, Product Bugs Share/Quarter, Top 10 Customers, Top 10 Components
- **Problem:** Updated Aug 22, 2025 — Daten 8 Monate alt, nur bis Q2 2025
- Auffällig: 40 Bugs >4 Wochen offen; Access Management SAP Signavio häufigste Komponente (185); 142 Bugs = identische Zahl wie im HEART Quarterly (gleiche Datenquelle)
- PPR-Kommentar (One Voice Dokument): selbe Datenbasis, selbe Definitions-Probleme wie im PPR
- **Thesis-Relevanz:** Hoch für Support/Quality KPIs — aber Freshness-Problem belegt Anforderung F02 (Near-Realtime)

#### Cloud Health & Reliability (CHR 2.0) ✅

- Corporate Dashboard — Processes & Information Technology
- **KPIs:** Cloud Operations: Avg Tenant Outage Min, Initial Customer Communication in 15min, SLA Violation %, % RCA Completion in 10 Days; Infrastructure: MTTR Infra, Avg Infra. Availability, Service Disruptions Count, % RCA Completion in 8 Days; YTD Facts: SWAT Count, Total Downtime Min
- Sichtbare Werte: SLA Violation **1,17%** (Ziel 0,5% — verfehlt), RCA Completion **87%** (Ziel 80% ✅), SWAT Count YTD: **10**, Infra. Availability Ziel: **99,90%**
- Filter: Solution Area, Dev Org (aktuell PE Ariba/Business — Signavio-Filter nicht bestätigt)
- **Thesis-Relevanz:** Hoch als Corporate-Layer; Relation zum Operational Status Dashboard: CHR = übergeordneter Cloud-Reliability-Layer, Operational Status = Signavio-spezifische Incident-Ebene

#### Product Standard Requirements P&E ✅

- Corporate — 9 Seiten; Quellsysteme: Sirius + HyCoM; Cut-off Apr 2026 (6-Monats-Fenster)
- **KPIs:** PSR Compliance-Status (Fulfilled vs. non-compliant) nach 4 PSR-Typen: Corporate, Mandatory, Integration, UX Consistency
- **Thesis-Relevanz:** Mittel — Compliance-Cluster (zusammen mit Corporate Requirements und EVM)

#### Corporate Requirements Dashboard ✅

- Corporate — 9 Seiten
- **KPIs:** CR Violations (Non-Security + Security), Current Status, LoB Overview, Time Trend, Violation Early Warning, BuLi Tabelle
- **Thesis-Relevanz:** Mittel — PSR + Corporate Requirements + EVM als ein Compliance-Integrations-Cluster

#### Product Standard Compliance Dashboard ⚠️

- Beim Durchgang nicht geladen — noch zu prüfen; inhaltlich vermutlich PSR-ähnlich

#### EVM — Infrastructure Vulnerabilities ⚠️

- SGSC Dashboard (EVM LOB Report), 2 Seiten (EVM Drill Down + EVM Trends)
- **KPIs:** L1 Goal Compliance (90d): Vulnerability-SLA nach Severity (Emergency/Critical/High/Medium/Low), Open vs. Fixed, Open vs. Risk Accepted, SLA Compliance per L3/L4 Unit, Avg. Vulnerability Age
- Partieller Zugang — neue EVM-Rolle nötig (EA Store)
- **Thesis-Relevanz:** Hoch — KPI-Kategorie Security/Vulnerabilities; Aktion: EA Store-Rolle beantragen

#### SAP Usage Analyzer | Product Analysis (Detailed) ✅

- Corporate — 7 Seiten: Overview, cACV, Solution Capabilities, Features, Solution Data Objects, Customers, Value Drivers
- **KPIs:** MAU-Trend (~278k), Customer Count (Live/Project/Shelfware), Active Scope (76%), Measured Product Scope (85%), Avg. Functional Footprint, Upcoming Renewals
- Aktuell auf LPR243 (S/4HANA Finance Cloud) gefiltert — kein Signavio-Filter bestätigt
- SAP Usage Analyzer Factsheet: ❌ SUNSET — "Please use the Detailed Product Analysis instead" → Mural-Link durch Oliver aktualisieren lassen

#### Signavio Micro Deliveries ✅

- SAP Jira — Signavio-spezifisch
- **KPIs:** Management Status RAG (361 GREEN, 0 RED/YELLOW), Progress of MD (55% Done, 695 Issues), Documentation Status (74% Done), X-Ray Status per Sub-Group, In Pre-Release Delivery Group Split, Product Board Info per Group (FIT/MXG/PA&M/NEXT)
- Sub-Groups: Platform Services, Process.AI, Transformation Enablement, SPG, M&C, Connectivity, Suite Essentials
- Filter: Current MD, Version/Delivery, Status, Assignee, Team, Labels, Sub-Groups, JQL
- ⚠️ Performance Notice aktiv ("bulk operations may be slow") — direkter Beleg für Stakeholder-Complaint aus REQUIREMENTS.md
- **Thesis-Relevanz:** Hoch — RAG-Status exakt das Signal, das der KPI-Hub surfacen soll; zweite Hauptquelle neben Operational Status; MVP-Kandidat

#### Product Excellence Portal (SAP Signavio) ✅ ⚠️

- Signavio-eigenes Portal mit 4 Kategorien: HEART, Revenue Insights, Product Management, Customer Insights
- HEART-Substruktur: Quarterly View / Half-Annual View / Annual View
- **KPIs sichtbar (HEART Quarterly Q2/2025):** PSAT 100%, DAU/MAU 10%, Added Content 5,4 Mio., Terminated Value 5.050 Tsd.€, Customer Reported Bugs 142, Added ACV Bookings 24,1 Mio.€, MAU 76,2 Tsd., Activated Users 1.392 Tsd.
- ⚠️ HEART-Dashboard deprecated: *"Due to deprecating classic SAC Stories this Dashboard is no longer supported."*
- ⚠️ Daten veraltet: Updated Apr 25, 2025 — 8 Monate alt
- Navigation: 3-Ebenen-Struktur (Portal → Kategorie → Kadenz → Dashboard) — widerspricht "Where do I find what?"-Anforderung
- **Thesis-Relevanz:** Sehr hoch — **einziger existierender Signavio Portal-Ansatz**. Deckt nur Product-KPIs ab (HEART, Revenue, Customer) — Engineering-KPIs (DORA, Delivery, Ops) fehlen komplett. Architekturelle Kernfrage für Kap. 6: Erweiterung dieses Portals oder eigenständige Lösung?

#### Product Experience Analytics Foundation (Collibra) ✅

- Collibra — Data for All Hub (SAP / 01-Product Development)
- **Typ:** Data Product (Derived, Gold-Qualität) — Datenbasis, kein Dashboard
- **Inhalt:** Qualtrics PX Survey-Daten + Mapping zu LPR, Solution Areas, Tenants, Customers
- SAP Datasphere Ready ✅, SAP Analytics Cloud Ready ✅, Architecture Execution CoE approved ✅
- **Thesis-Relevanz:** Mittel — zeigt BDC-Stack-Funktionsweise in der Praxis (Qualtrics → Collibra → Datasphere → SAC)

#### Signavio Dashboards (Gainsight) ❌

- Kein Zugang — Zugangsdaten bei Janine erfragen (Freitag 24.04.)

#### SAP Signavio Release Management Security (Grafana) ❌

- Kein Zugang — Zugangsdaten bei Janine erfragen (Freitag 24.04.)

#### Product 360 ❌

- Global Adoption & Experience CoE (2 Seiten)
- **KPIs (aus Fehlermeldung/Übersicht):** Customers, Usage (MAU, Active Scope), AI Usage (Base/Premium AI Features), PX (PSAT, Usefulness, Ease of Use), Commercials (Cloud Revenue, Backlog, Bookings, Pipeline), Support (Call Rate, Avg Days to Solve, Customer Effort Score)
- Fehler: "Not authorized to the data. Please request authorization in EA Store. Up to 48h propagation."
- **Thesis-Relevanz:** Hoch als Referenz — konzeptionell der vollständigste KPI-Hub für Product-KPIs; fehlt: Engineering/DORA

#### Adoption Monitor 2.0 ❌

- Kein Zugang (Berechtigungen fehlen). Wahrscheinlich Pendo-basiertes Dashboard in SAC (vgl. Pendo Analytics Playbook)
- Frage an Janine: Wie beantragen? Wer ist Owner?

#### Rolling Calendar of Cross Initiatives (Wiki) ✅

- Wiki@SAP — Anna Maria Muhs, zuletzt Apr 08, 2026; Migration zu ProductBoard geplant
- **Typ:** Statische Transparenzschicht — kein Dashboard, keine KPI-Daten
- Thesis-relevante Initiativen: Unified Metering (non-billable usage), Hyperspace/CircleCI Migration (Beppler Christopher), HAIM (Auth/RBAC), Data & Analytics Initiative (Barbara Schories)
- FAQ-Zitat für Kap. 4: *"If BDC integration is prioritized... PA&M and MxG would add the relevant data-product deliveries in NEXT"*

#### E2E Portfolio Planning Dashboard / E2E Portfolio QBR Dashboard ❌

- Beide Links defekt ("Diese Datei konnte nicht gefunden werden")
- Frage an Oliver: Existieren noch? Wer ist Owner?

#### Weitere (geringer Relevanz)

- **CACV Dashboard** ⚠️ — YTD cACV, YoY Growth; auf BTP gefiltert, kein Signavio-Datensatz. Gering: GtM/Financials
- **CACV Single Customer** ⚠️ — Single-Customer Drilldown; kein Signavio-relevanter Datensatz. Gering: GtM/Sales
- **CPA Planning & Adoption Insights** ✅ — SAP-weit (9.586 Issues: BTP, AI, Ariba); nicht Signavio-spezifisch. Gering.
- **Signavio Dashboards (SAC-Ordner)** ✅ — Navigationscontainer; Unterordner: Content, Jira Dashboards, License and Feature, Product Usage Dashboards, VAD + 2 Stories. Mit Oliver klären, welche Unterordner Engineering-relevant sind.

### B.5 Gesamtfazit Mural-Analyse

**Zahlen:** Von ~25 Links: ~8 vollständig zugänglich, ~8 kein Zugang, ~3 deprecated/veraltet, ~2 defekte Links.

| # | Kernbefund | Thesis-Kapitel |
|---|---|---|
| 1 | **Fragmentierung messbar:** 7 Systeme (SAC, Jira, Collibra, Gainsight, Grafana, Wiki, SharePoint), kein einheitlicher Einstieg | Kap. 1 + 4 |
| 2 | **RBAC-Problem real:** Fast jedes 3. Dashboard nicht zugänglich (CAM, EA Store, Sirius-Mitgliedschaft) | Kap. 4 + 5 |
| 3 | **DORA-Metriken fehlen komplett** — kein einziges Dashboard für Deployment Frequency, Lead Time, CFR, MTTR als DORA | Kap. 4 + 5 (Lücke) |
| 4 | **Freshness-Problem:** HEART veraltet (8 Monate), Bugs-Dashboard (8 Monate), deprecated Komponenten | Kap. 4 |
| 5 | **Stärkste Quellen:** Operational Status Dashboard (ServiceNow) + Jira Micro Deliveries | Kap. 4 + 8 (MVP-Quellen) |
| 6 | **Product Excellence Portal = Präzedenzfall:** Portallösung existiert für Product-KPIs — Engineering fehlt komplett | Kap. 6 |

---

## C — Parallele Initiativen

### C.1 #OneDashboard Vision (Oliver Timm)

> Quelle: "one-signavio-metrics-dashboard.pdf" — Oliver Timm.

**Vision:** *"We have #OneDashboard with all relevant KPIs visualized in various categories that everyone can consider while deciding."*

Aktuell: monatlicher KPI-Report als PDF (Headcount, Financials, Release Management). Mehrere parallele Initiativen ohne Harmonisierung.

**KPI-Kategorien (vollständige Liste):**

| Kategorie | KPIs |
|---|---|
| **GTM** | Renewal Rate, Net Retention Rate, Licensed Customers, Health Score |
| **Service** | Value of Services Sold, Win Rate, CSAT, Utilization, Service-to-License Attach Rate, Profitability |
| **People** | FTE/Heads, Diversity (Gender, Early Talent, Females in Mgmt), Attrition Rate, Career Level |
| **Usage** | Software- und Feature-Nutzung (nicht weiter spezifiziert) |
| **Delivery (DORA + Jira)** | Deployment Frequency, Lead Time for Changes, Change Failure Rate, MTTR, Throughput, Cycle Time |
| **Release Management** | Vulnerabilities, PSR Compliance, Key Customer Issues / Outages |
| **Financials** | P&L Statement, Actuals, Budget, Forecast |

**Bestehende Initiativen:**

| Initiative | Owner | Status | Beschreibung |
|---|---|---|---|
| **COO Cross Team** | Jens Hildenbrand | **On Hold** (Re-Org) | Digital Boardroom für Rouven, Gero, LT; Standard-KPIs via ID&A + Signavio-spezifisch |
| **GTM** | Julius Meinl | Laufend | E2E Steering Model, High-level Health Overview für Senior Management |
| **Process Intelligence** | Björn Wagner, Rohini Geetha Soman Nair | Laufend | Jira-Daten (Release Prediction), Usage Data mit Event Logs |
| **DORA & QA Metrics** | Stefan Popescu et al. | OKR, nicht voll besetzt | DORA & QA Metrics Dashboard |
| **Process Insights** | — | Produktiv | 3 Cloud Reporting Dashboards: SAP Signavio Ops, SAP Process Insights, Solution Area SAP Signavio |
| **PM&Strategy** | — | Migration geplant | Data-Driven Product Mgmt, aktuell on-prem Tableau → SAC |

**Hindernisse (aus Dokument):**
1. Verschiedene Datenquellen → Integration komplex
2. Zu viel manueller Aufwand → Aggregation händisch
3. Access Rights → unterschiedliche Zugriffsrechte, keine Policy
4. Nicht genug Kapazität → COO-Office unterbesetzt
5. Kein klares Ownership → keine dedizierte Verantwortung

> **Thesis-Relevanz:** Die 5 Hindernisse sind die direkte empirische Basis für Kap. 4 (Problemfelder) und Kap. 5 (Anforderungen). Insbesondere Hindernis 3 (Access Rights) bestätigt RBAC als Kernforderung.

### C.2 VoC „One Voice" (Lea Reib / Oliver Timm / Janine Steidelmüller)

> Quelle: "SAP Signavio Voice of the Customer Program 'One Voice' – Alignment Sheet", 05.11.2025.

**Problem Statement (direkt):** *"Signavio's Product & Engineering Department operates without unified, actionable visibility into customer satisfaction and experience. Customer insights are immature within development and engineering workflows."*

**Scope:** CX/VoC-Schicht — Customer Satisfaction, Feature Adoption, PSAT. **Zielgruppe:** PLT, EPTs.

**Verhältnis zum KPI-Hub:**

| Dimension | One Voice | KPI-Hub (diese Arbeit) |
|---|---|---|
| Scope | CX/VoC: Customer Satisfaction, Feature Adoption, PSAT | Engineering + Ops + DORA + Compliance + Usage |
| Zielgruppe | PLT, EPTs | Senior Management (Oliver) |
| Status (Nov 2025) | Demo-Dashboard in Metabase | Bachelorarbeit + MVP |
| Overlap | HEART-Metriken, Customer Bugs, Feature Adoption | ← identische KPI-Kategorien |

**Fazit:** One Voice und KPI-Hub sind **komplementär** — One Voice = CX/VoC-Schicht, KPI-Hub = Engineering + Ops-Schicht. Beide kämpfen gegen dasselbe Problem (PPR-Fragmentierung). Für Kap. 4 und 6 ist die Existenz von One Voice ein weiterer Beleg für den Handlungsbedarf.

**Neue Person:** Lea Reib — Co-Autorin, Product Excellence / VoC-Initiative. Potenzielle Interviewpartnerin für Kap. 5.

**One Voice vs. PPR — Die 4 Differenziatoren (aus Dokument):**
1. Dashboards mit Live-Daten (statt Quartalsschnappschuss)
2. Real-time Updates durch Datenintegrationen (statt manuellem Export)
3. Korrelierte Daten aus mehreren Quellen (statt Silos)
4. Weniger manueller Aufwand → schnellere Insights

---

## D — Lösungskandidaten (→ Kap. 6)

### D.1 SAP BDC-Stack — Offizieller SAP-Pfad

> Quellen: EKG-Recherche (21.04.2026) + Svitlana-Präsentation "Introducing BDC" (05.02.2026, Svitlana Vlasova) + Svitlana-Meeting (22.04.2026).

#### Kernkomponenten

| Komponente | Rolle im Stack |
|---|---|
| **SAP Datasphere (DSP)** | Datenschicht: Integration, Modellierung, Semantik — zentrale persistente Schicht |
| **SAP Analytics Cloud (SAC)** | Consumption Layer: Dashboards, Stories, KPI-Modellierung, „My Metrics"/Alerts, Planung |
| **SAP Signavio Process Insights** | Prozess-/Service-KPIs: Jira + ServiceNow als Quellsysteme produktiv; Metriken z.B. Avg Resolution Time, Breached SLA Ratio |
| **Collibra** | Data Governance, Catalog, Lineage, Qualität, Privacy — **kein SAP-Produkt, aber fester BDC-Bestandteil** |
| **SAP Databricks** | AI/ML, Advanced Data Engineering (optional, nicht für KPI-Hub primär relevant) |

#### Datasphere 3-Schichten-Architektur

| Schicht | Zweck |
|---|---|
| 1 — Input Layer | Rohdaten 1:1 aus Quellsystem, persistiert |
| 2 — Transformation Layer | Business Logic: Joins, Aggregation, Harmonisierung → FACT Views |
| 3 — Output Layer | Business-ready: Measures, Keys, Hierarchien, Analytic Models → SAC-Consumption |

**Datenfluss:** Quellsystem → Datasphere (Input → Transform → Output) → Analytic Model → SAC (Live Connection → Story).
Auch möglich: CSV-Upload in Datasphere (für noch nicht integrierte KPIs).

#### Data Products (Collibra-Konzept)

Standardisierte, wiederverwendbare „business-ready" Datenassets. Werden in Collibra katalogisiert (Suche, Metadata, Lineage, Ownership, SLAs).
Lifecycle: Ideate → Initiate → Build & Govern → Publish → Consume → Maintain → Retire.
**Referenzprojekt intern:** „BDC Operations Insights — Goals Tracking" (Svitlana Vlasova): Product Satisfaction, Active Users, Cloud Availability → Data Products in Collibra → DSP → SAC.

#### BDC Adoption Program

SAP nutzt BDC intern als „Customer Zero". Spaces in Datasphere: „Goals Tracking", „BDD Goals Tracking Foundation", „General Manager 360". Mentoring-Programm für Citizen User Adoption. Ansprechpartnerin: Svitlana Vlasova (s.vlasova@sap.com, von Janine empfohlen).

#### Konnektivität Non-SAP-Quellen

| Quelle | Empfohlener Pfad | Reife |
|---|---|---|
| Jira | Signavio-Adapter (produktiv) oder REST API (Replication Flows) | Signavio: produktiv ✅ |
| ServiceNow | Signavio-Adapter (produktiv) oder REST API | Signavio: produktiv ✅ |
| CircleCI | REST API (Build/Pipeline/Test-Reports) oder File-Export | REST: Roadmap/Feature |
| Gainsight | REST API oder File-Export | REST: Roadmap/Feature |
| Pendo | Data Sync / REST API | Zu klären |

Generisch: **File/Object Store Staging** (CSV/Parquet → Datasphere) ist robuster Fallback für alle Quellen.
Schnellster Weg für Issue-KPIs: Quelle → **Signavio Process Insights** → SAC (Jira/ServiceNow als Quellsysteme bereits vorhanden).

#### Freigaben / Restriktionen

BDC-Kernbausteine (Datasphere, SAC, Signavio): üblicherweise unkritisch.
Non-SAP-SaaS-Quellen: Security/Compliance-Freigabe nötig (OAuth, Datenklassifizierung, Datenresidenz).
Konkrete Freigabeliste für Signavio Engineering: bei Janine/Svitlana erfragen.

### D.2 EKX (Enterprise Knowledge Exploration)

> Quelle: Janine Steidelmüller, 21.04.2026 — explizit zur KPI-Hub-Bewertung vorgeschlagen.

EKX basiert auf dem **Enterprise Knowledge Graph (EKG)**. Spring Release April 2026 erweitert EKX zur „Creation Engine": Generierung von Dashboards, Diagrammen, PowerPoints, Code — geerdet in SAP-Inhalten. Kein KPI-Persistenz- oder Visualisierungstool (kein Datasphere/SAC-Ersatz). Potenzielle Rolle: **Deliverable-Layer** on top der KPI-Datenbasis. Svitlana kennt EKX nicht — kein BDC-Einsatz bekannt. Zu klären: Kann EKX live auf KPI-Datenquellen zugreifen, oder nur auf statische SAP-Inhalte?

### D.3 SAP Build Work Zone

Zentrales Portal-Layer („Single Pane of Glass") zur Einbettung von SAC-Stories, Signavio-Kacheln, Dokumentation. Kein expliziter Beleg für Signavio-Engineering-KPI-Hub-Einsatz. Technisch naheliegend als Portal-Option. SAP Mobile Start: Mobile Exponierung von SAC-KPI-Kacheln (optional, falls Mobile-First für Leadership relevant).

### D.4 SAP Integration Suite

Standardisierte Adapter (Open Connectors / Cloud Integration) für Non-SAP-Quellen (Jira, ServiceNow, Gainsight, CircleCI) via REST, Webhooks, Files. EKG-Beleg für Signavio-Bezug vorhanden. → Primärer Ingestion-Pfad für Non-SAP-Quellen (Alternative/Ergänzung zu Signavio-Adaptern).

### D.5 Pendo Analytics (als eigenständiger Tool-Kandidat)

Pendo als **Standalone-Dashboard-Tool** (nicht nur als Datenquelle). Eigene Dashboard-Typen: Feature Adoption, Application Overview, Executive Readout, Roadmap Evidence. Vorteil: stärkste native Quelle für Product Usage KPIs. Nachteil: kein integrierter Portal-Layer, kein Engineering/DORA-Coverage, Standalone-UX begrenzt.

Für KPI-Hub-Überlegungen: Pendo als **Quellsystem** (Data Out → Datasphere → SAC) ist wahrscheinlicher als Pendo als Zieldashboard.

### D.6 Metabase

> Quelle: One Voice Alignment Sheet (05.11.2025) — Demo Dashboard „ONE VOICE @SAP SIGNAVIO" in Metabase.

Open-Source BI / Self-Service Analytics Tool (SQL-basiert). Oliver und Janine nutzen Metabase für das One Voice Demo-Dashboard — impliziter Hinweis, dass BDC-Stack für VoC-Use-Case als zu schwer empfunden wird. **SAP-Freigabe unklar** — nicht im offiziellen BDC-Stack. Interessante Spannung für Kap. 6: BDC (offiziell, komplex) vs. Metabase (leichtgewichtig, schnell, aber Compliance fraglich).

### D.7 Weitere SAP-Tool-Kandidaten

- **SAP Cloud ALM:** IT-Ops- und Projekt-KPIs (Incidents, Deployments, Test Coverage). EKG-Beleg für Signavio-Integration. → Potenzielle Datenquelle für Operations-KPIs.
- **SAP HANA Cloud:** Für hochfrequente oder komplexe Berechnungen jenseits Datasphere-Standard; Near-Real-Time-Szenarien.
- **SAP Solution Manager — Focused Insights:** Vorkonfigurierte IT-Betriebs-Dashboards (nur relevant falls SolMan noch aktiv).
- **LeanIX:** IT-Portfolio-/Architektur-KPIs; Einbettung in SAC/Build Work Zone als Kontextebene.
- **SAC Data Steer** (via BDC → SAC): Von Svitlana erwähnt als neuer Tool-Kandidat — näher ansehen.

---

## E — Integrationsarchitektur (→ Kap. 6)

### E.1 Empfohlene Zielarchitektur (vorläufig, aus EKG-Recherche abgeleitet)

| Schicht | Tool(s) | Reife |
|---|---|---|
| Ingestion Non-SAP | Integration Suite (Open Connectors) + Signavio-Adapter (Jira/ServiceNow) | Signavio: produktiv |
| Persistenz/Semantik | SAP Datasphere | Produktiv |
| Prozess-/Service-KPIs | SAP Signavio Process Insights | Produktiv |
| Ops-/Projekt-KPIs | SAP Cloud ALM → Datasphere | Zu prüfen |
| Visualisierung/Monitoring | SAP Analytics Cloud (Stories, My Metrics, Alerts) | Produktiv |
| Portal/Experience | SAP Build Work Zone | Zu prüfen |
| Creation/Deliverables | EKX | Spring Release 2026 |
| Mobile | SAP Mobile Start (optional) | Produktiv |

> Diese Architektur ist eine Hypothese auf Basis der EKG-Recherche (21.04.) — noch nicht durch Praxis-Validierung bestätigt. Wird in Kap. 6 + 7 evaluiert.

---

## F — Kritischer Fit-Check (→ Kap. 7)

BDC ist primär für ERP/S/4HANA konzipiert; Signavio-Engineering-Quellsysteme sind dominant **Non-SAP** (Jira, ServiceNow, Gainsight, CircleCI, Pendo/Qualtrics). Es gibt keinen „Plug-and-play"-Pfad — Integrationsaufwand für REST-API-Ingestion ist real.

Dies ist ein zentrales **Machbarkeitskriterium** für das Scoring-Modell (Kap. 7) und ein „erschwerender Faktor im konkreten Einsatzfall" i.S. Sachses Erwartungen.

Gleichzeitig: Jira und ServiceNow sind bereits produktiv als Signavio-Adapter in Signavio Process Insights eingebunden — das ist der schnellste BDC-native Integrationspfad für die zwei stärksten KPI-Quellen.

---

## G — Offene Fragen & Aktionen

| Priorität | Aktion | An wen | Status |
|---|---|---|---|
| **Morgen (24.04.)** | Pendo-Zugang / Adoption Monitor 2.0 — Wer ist Owner? | Janine | Offen |
| **Morgen (24.04.)** | Metabase One Voice Demo-Dashboard — SAP-freigegeben? Zugang? | Janine | Offen |
| **Morgen (24.04.)** | Gainsight Zugangsdaten | Janine | Offen |
| **Morgen (24.04.)** | Grafana Zugangsdaten | Janine | Offen |
| **Morgen (24.04.)** | E2E Portfolio Links (Owner + Status) | Janine/Oliver | Offen |
| **Morgen (24.04.)** | SAP Usage Analyzer + CHR: Signavio-Filter vorhanden? | Janine | Offen |
| **Morgen (24.04.)** | Mural-Link Usage Analyzer aktualisieren (Factsheet → Detailed) | Oliver | Offen |
| **Morgen (24.04.)** | Lea Reib — Kontakt für Kap. 5 Interview sinnvoll? | Janine | Offen |
| **Nächste Woche** | DORA-Metriken: Gibt es ein Dashboard? (Stefan Popescu Initiative) | Oliver | Offen |
| **Nächste Woche** | SAP_Signavio_Dashboards Unterordner (Jira, Product Usage) durchgehen | Oliver | Offen |
| **Nächste Woche** | Qualtrics API-Zugang — Near-Realtime PSAT möglich? | Janine | Offen |
| **Nächste Woche** | Pendo Data Sync → Datasphere: möglich? | Janine/Oliver | Offen |
| **EA Store (48h)** | Product 360 Access beantragen | Selbst | Beantragt? |
| **EA Store (48h)** | EVM neue Rolle beantragen | Selbst | Beantragt? |

---

## H — Quellenübersicht

| Quelle | Typ | Datum | Von |
|---|---|---|---|
| EKG-Recherche (Enterprise Knowledge Graph) | KI-gestützte Recherche | 21.04.2026 | — |
| Svitlana Vlasova — Meeting | Meeting-Notizen | 22.04.2026 | Janine (Empfehlung) |
| Svitlana Vlasova — "Introducing BDC" | Präsentation (INTERNAL) | 05.02.2026 | Svitlana |
| Oliver Timm — Mural Dashboard-Links | Dashboard-Analyse (INTERNAL) | 23.04.2026 | Oliver |
| Oliver Timm — #OneDashboard PDF | Dokument (INTERNAL) | (undatiert) | Oliver |
| Oliver Timm — Pendo Analytics Playbook | Playbook (INTERNAL) | 23.04.2026 | Oliver |
| Lea Reib / Oliver Timm / Janine — One Voice Alignment Sheet | Alignment-Dokument (INTERNAL) | 05.11.2025 | Oliver |
