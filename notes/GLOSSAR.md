# Glossar — KPI-Hub-Bachelorarbeit

Persönliche Begriffsbasis für die Bachelorarbeit und Praxisphase.
Struktur: Begriff → Definition / Abgrenzung → ggf. Quelle / Kontext.

---

## Fachbegriffe (Bachelorarbeit)

**KPI (Key Performance Indicator)**
Messbare Kennzahl zur Bewertung des Erfolgs einer Organisation, eines Prozesses oder einer Maßnahme gegenüber definierten Zielen.

**KPI-Hub**
Zentraler Zugangspunkt („Single Pane of Glass") der Kennzahlen aus mehreren Quellsystemen integriert oder föderiert bereitstellt, ohne zwingend eine zentrale Datenhaltung vorauszusetzen.

**Single Pane of Glass**
Metapher für eine einheitliche Benutzeroberfläche, die Informationen aus verschiedenen Quellen konsolidiert darstellt.

**Dashboard-Föderation / Embedding**
Integrationsansatz, bei dem bestehende Dashboards anderer Systeme per iFrame oder SDK in eine übergeordnete Oberfläche eingebettet werden, ohne die Daten selbst zu kopieren.

**ETL (Extract, Transform, Load)**
Prozess zur Datenintegration: Daten werden aus Quellsystemen extrahiert, transformiert und in ein Zielsystem geladen.

**API (Application Programming Interface)**
Schnittstelle, über die Softwarekomponenten miteinander kommunizieren. Im Kontext der Arbeit relevant für den programmatischen Datenabruf aus Quellsystemen.

**BI (Business Intelligence)**
Technologien, Prozesse und Methoden zur Sammlung, Integration, Analyse und Präsentation von Geschäftsdaten zur Entscheidungsunterstützung.

**RBAC (Role-Based Access Control)**
Zugriffskontrollmodell, bei dem Berechtigungen auf Basis von Rollen vergeben werden. Zentrales Kriterium in dieser Arbeit.

**Data Governance**
Rahmenwerk aus Verantwortlichkeiten, Regeln und Kontrollen für den Umgang mit Daten innerhalb einer Organisation. Beeinflusst welche Integrationsformen zulässig sind.

**Fragmentierung (Systemlandschaft)**
Zustand, in dem Informationen und Kennzahlen auf mehrere nicht integrierte Systeme verteilt sind, was eine konsistente Gesamtsicht erschwert.

**Scoring-Modell**
Bewertungsrahmen, der Optionen anhand gewichteter Kriterien vergleichbar macht und eine transparente Entscheidungsgrundlage liefert.

**Sensitivitätsanalyse**
Methode zur Überprüfung der Robustheit einer Entscheidung: Wie verändert sich das Ergebnis wenn Kriteriengewichtungen variiert werden?

**Design Science Research (DSR)**
Wissenschaftlicher Forschungsansatz, bei dem Erkenntnisgewinn durch Konstruktion und Evaluation eines Artefakts entsteht. Methodische Grundlage dieser Arbeit (nach Heinzl + Riedl).

**Artefakt (DSR)**
Im Design-Science-Kontext: ein durch den Forschungsprozess konstruiertes Objekt (hier: Bewertungsmodell + MVP), das das Problemverständnis illustriert und Lösungspotenziale aufzeigt.

**MVP (Minimum Viable Product)**
Minimal funktionfähiges Produkt zur Verifikation zentraler Machbarkeitsannahmen und technischer Risiken mit möglichst geringem Aufwand.

---

## SAP / Signavio — Praxiskontext

**SAP Signavio**
SAP-Tochter für Business Process Management und Process Intelligence. Der Bereich „Signavio Product & Engineering" ist der organisatorische Kontext dieser Arbeit.

**SAP Analytics Cloud (SAC)**
Cloud-basierte SAP-Lösung für BI, Planung und Predictive Analytics. Eine der zentralen KPI-Quellen im Ist-Zustand.

**JIRA**
Projektmanagement- und Issue-Tracking-Tool (Atlassian). Im Kontext: Quelle für Sprint-Performance-Metriken und Ticketlage.

**ServiceNow**
IT-Service-Management-Plattform. Im Kontext: Quelle für operative Kennzahlen (z.B. Incident-Metriken).

**SAP BTP (Business Technology Platform)**
Plattform für die Entwicklung und Integration von SAP-Anwendungen. Potenziell relevant als technische Basis für den KPI-Hub.

**Gainsight**
Customer-Success-Plattform (GtM-seitig). Quelle für Customer-Success-KPIs wie Retention, Adoption, Nutzungsmetriken.

**BDC (Business Data Cloud)**
SAP-Produkt zur Vereinheitlichung und Bereitstellung von Unternehmensdaten. Referenzarchitektur für KPI-Management: Datenbasis (SAP Datasphere), Visualisierung/Monitoring (SAP Analytics Cloud), Prozess-KPIs (SAP Signavio Process Insights). Primär für ERP/S/4HANA konzipiert; Non-SAP-Quellen (Jira, ServiceNow etc.) per Konnektoren/REST-API einbindbar. Relevant für Kap. 4 (Systemlandschaft) und Kap. 6 (Lösungsraum).

**SAP Datasphere**
Zentrale semantische Datenschicht innerhalb der BDC. Persistiert KPI-Fakten, Dimensionen und Datenprodukte; harmonisiert SAP- und Non-SAP-Quellen über Konnektoren und Replication Flows. Keine dedizierten Out-of-the-box-Konnektoren für Jira/ServiceNow/CircleCI — Integration via REST API oder File-Staging.

**EKX (Enterprise Knowledge Exploration)**
SAP-internes Tool auf Basis des Enterprise Knowledge Graph (EKG). Spring Release 2026: Evolution zur "Creation Engine" — generiert Dashboards, Diagramme, PowerPoints, Code aus SAP-Inhalten. Von Janine als Tool-Kandidat für KPI Hub vorgeschlagen (21.04.2026). Zu klären: Konnektivität zu operativen Datenquellen.

**PPR (Product Performance Review)**
Internes SAP-Reporting-Format. Wird als zu statisch, slide-basiert und nicht engineering-spezifisch bewertet. Kein direkter Link zu engineering-seitigen KPIs.

**PI (Program Increment / PI Planning Tool)**
Im SAP-Signavio-Kontext: Tool für Flow Metrics auf Basis von JIRA-Daten. Datenqualität wird von Stakeholdern als unzuverlässig eingestuft.

**Product 360**
Internes SAP-Produkt-Übersichts-Dashboard.

**P&E Fundamentals Dashboard**
Internes Engineering-Dashboard für grundlegende P&E-Metriken.

**Micro Deliveries**
Internes Tracking-System für Delivery-Metriken auf Teamebene.

**DORA-Metriken (DevOps Research and Assessment)**
Vier Leitmetriken für Software-Delivery-Performance: Deployment Frequency, Lead Time for Changes, Change Failure Rate, Time to Restore Service. Im SAP-Signavio-Kontext kaum noch aktiv genutzt.

**FLOW-Metriken**
Kennzahlen zur Messung des Wertflusses durch Engineering-Prozesse (Flow Velocity, Flow Efficiency, Flow Load, Flow Time, Flow Distribution). Ergänzt DORA um einen businessseitigen Blick.

**HEART-Framework**
Google-UX-Messmethode: Happiness, Engagement, Adoption, Retention, Task Success. Im Kontext für Produkt-Adoption-KPIs relevant.

**MAU / DAU (Monthly/Daily Active Users)**
Nutzungsmetriken zur Messung von Produktaktivität. MAU = Monatlich aktive Nutzer, DAU = Täglich aktive Nutzer.

**ACV (Annual Contract Value)**
Jährlicher Vertragswert eines Kunden. Wichtige Business-KPI im SAP-Signavio-Kontext.

**PSAT (Predictive/Partner Satisfaction Score)**
Zufriedenheitskennzahl. Genaue Definition im SAP-Signavio-Kontext zu klären.

**EMT (Engineering Management Team)**
Leitungsgremium im Engineering-Bereich. Relevante Zielgruppe für Leadership-KPIs.

**EPT / PLT**
Engineering-interne Teambezeichnungen (Engineering Productivity Team / Product Leadership Team). Genaue Definition zu verifizieren.

**VT-STAR**
SAP-internes Studentenprogramm. Laut Olivers Dokument soll der KPI-Hub-MVP mit einem VT-STAR-Studenten umgesetzt werden.

---

## Abkürzungen

| Kürzel | Ausgeschrieben |
|--------|----------------|
| KPI | Key Performance Indicator |
| API | Application Programming Interface |
| ETL | Extract, Transform, Load |
| BI | Business Intelligence |
| MVP | Minimum Viable Product |
| RBAC | Role-Based Access Control |
| DSR | Design Science Research |
| SAC | SAP Analytics Cloud |
| BTP | SAP Business Technology Platform |
| PoC | Proof of Concept |
