# Meeting-Vorbereitung: Svitlana Vlasova — 22. April 2026

**Kontakt:** Svitlana Vlasova (s.vlasova@sap.com) — SAP-intern, BDC/SAC-Expertin  
**Tipp von:** Janine Steidelmüller (21.04.2026)  
**Ziel:** BDC/SAC Tool-Überblick für Praxisphase + Bachelorarbeit

---

## Was ich schon weiß (Stand 21.04. — nicht nochmal fragen)

### BDC-Architektur (recherchiert)
- **SAP Datasphere** = zentrale semantische Schicht, Persistenz, Datenprodukte
- **SAP Analytics Cloud (SAC)** = KPI-Modellierung, Stories, "My Metrics"/Watchlist, Alerts
- **SAP Signavio Process Insights** = prozessnahe KPIs; Jira + ServiceNow als Quellsysteme bereits vorhanden
- **SAP Integration Suite** = Non-SAP-Ingestion (Open Connectors, REST-Adapter)
- **SAP Build Work Zone** = Portal-Layer, Einbettung von SAC-Stories
- **SAP Cloud ALM** = Ops/Projekt-KPIs, explizit Signavio-integriert

### Bekannte offene Punkte
- Non-SAP-Konnektoren (Jira, ServiceNow, CircleCI, Gainsight): kein out-of-the-box confirmed → REST via Replication Flows oder Signavio-Adapter
- REST via Replication Flows: im EKG als Roadmap/Feature Item — produktiv möglich, aber Reifegrad unklar
- EKX: Relevanz unklar (Creation Engine vs. KPI-Persistenz-Tool)

---

## Fragen an Svitlana

### Priorität 1 — Kernfragen für Thesis (Kap. 6 Lösungsraum + Kap. 7 Scoring)

1. **Konnektivität Non-SAP (konkret für Signavio Engineering):**  
   Gibt es produktiv genutzte Konnektoren oder erprobte Patterns für Jira, ServiceNow, CircleCI, Gainsight in Datasphere — oder ist REST via Replication Flows aktuell noch Roadmap?

2. **Reife REST-basierte Replication Flows:**  
   Wie produktionsreif sind REST-API-basierte Replication Flows in Datasphere heute (April 2026)? Was sind die bekannten Einschränkungen (Rate Limits, Paginierung, Delta, Retry)?

3. **SAC "My Metrics" / KPI-Watchlist für Engineering-KPIs:**  
   Ist "My Metrics" / KPI-Monitoring in SAC auch für Non-ERP/Non-SAP-Quellen praktisch nutzbar, oder ist die Erfahrung hauptsächlich S/4HANA-lastig?

4. **Freigabe / Compliance für Non-SAP-Quellen:**  
   Welche Security/Compliance-Freigaben brauche ich für den Zugriff auf externe Quellen (Jira/ServiceNow/Gainsight) aus Datasphere heraus — wo muss ich anfragen?

### Priorität 2 — Architektur-Entscheidungen

5. **Direktpfad Signavio Process Insights → SAC:**  
   Kann ich Signavio-Process-Insights-KPIs direkt in SAC konsumieren (ohne eigene Datasphere-Schicht)? Empfehlenswert oder eher Anti-Pattern?

6. **Datasphere vs. SAC als "Single Source of Truth":**  
   Für einen Engineering-KPI-Hub: Modellierung primär in Datasphere (semantische Schicht) + SAC als Visualisierung, oder gibt es Cases wo die KPI-Logik direkt in SAC lebt?

7. **BW Bridge Relevanz:**  
   Für einen reinen Engineering-/Non-SAP-KPI-Use-Case — ist BW Bridge relevant oder kann ich das ignorieren?

### Priorität 3 — Kontext / Referenzen

8. **Referenzprojekte Engineering-KPIs:**  
   Gibt es SAP-interne BDC-Projekte die Engineering-/DevOps-KPIs (DORA-Metriken, Ticket-KPIs, Build-KPIs) abbilden — nicht ERP? Oder kennt Svitlana jemanden der das gemacht hat?

9. **EKX einschätzen:**  
   Janine hat EKX als Tool-Kandidat für den KPI Hub genannt. Wie schätzt Svitlana EKX ein — komplementär zum BDC-Stack oder eigener Ansatz? Kann EKX live auf KPI-Daten zugreifen?

10. **Typischer Onboarding-Weg:**  
    Was empfiehlt Svitlana als Einstieg um BDC/Datasphere/SAC hands-on zu lernen — gibt es einen Trial-Tenant oder einen SAP-internen Sandbox?

---

## Kontext (kurz erklären am Anfang)

- Bachelorarbeit: Entscheidungsmodell zur Auswahl eines KPI-Hub-Integrationsansatzes für Signavio Engineering
- Quellsysteme: Jira, ServiceNow, CircleCI, Gainsight (dominant Non-SAP)
- Ziel: Scoring-Modell das BDC vs. alternative Ansätze bewertet + MVP
- Janine hat BDC als Referenzarchitektur genannt und Svitlana als Ansprechpartnerin empfohlen
- Machbarkeit (Umsetzbarkeit, Integrationsaufwand) ist laut Janine das wichtigste Kriterium

---

## Nach dem Meeting

- [ ] Notizen in MEETINGS.md eintragen
- [ ] TOOLS.md mit neuen Erkenntnissen aktualisieren (insb. Reifegrad Konnektoren)
- [ ] THESIS_STATUS.md aktualisieren (offene Punkte abhaken)
- [ ] Commit + Push
- [ ] KI_PROTOKOLL.md: Eintrag für Meeting-Vorbereitung (KI-Unterstützung)
