# KPI-Hub — Architekturkonzept und Umsetzungsplanung

Stand: 23. April 2026 — vorläufig, noch nicht durch Praxis-Validierung bestätigt.

---

## 1 — Zielarchitektur: 4-Schichten-Modell

```
┌─────────────────────────────────────────────────────────┐
│  Schicht 4 — Deliverables       EKX                     │
│  Automatische Report-/PPT-Generierung aus KPI-Daten     │
└────────────────────────┬────────────────────────────────┘
                         │ (Datenzugriff noch zu klären)
┌────────────────────────▼────────────────────────────────┐
│  Schicht 3 — Portal             SAP Build Work Zone     │
│  Single Pane of Glass — bettet SAC-Stories ein          │
└────────────────────────┬────────────────────────────────┘
                         │ Live-Embedding
┌────────────────────────▼────────────────────────────────┐
│  Schicht 2 — Visualisierung     SAP Analytics Cloud     │
│  Stories, KPI-Modelle, My Metrics, Alerts               │
└────────────────────────┬────────────────────────────────┘
                         │ Live Connection
┌────────────────────────▼────────────────────────────────┐
│  Schicht 1 — Daten              SAP Datasphere          │
│  Integration, Harmonisierung, Data Products             │
└────────────────────────┬────────────────────────────────┘
                         │
        ┌────────────────┼────────────────────────┐
        ▼                ▼                        ▼
   Jira / ServiceNow   Pendo / Qualtrics     Gainsight / Grafana
   (Signavio-Adapter ✅) (REST API / File)   (REST API — zu klären)
```

---

## 2 — Quellsystem-Mapping

Detailliertes Quellsystem-Mapping siehe [TOOLS.md, Sektion A](TOOLS.md#a--quellsysteme-ist-zustand).

---

## 3 — Phasenplan

### Phase 1 — MVP (Ziel: Ende Juni 2026)

**Fokus:** Die zwei bereits integrierten Quellen nutzen. Kein neuer Integrationsaufwand.

| Baustein | Inhalt | Tool |
|---|---|---|
| Daten | Jira-Daten (RAG, Delivery-Status) + ServiceNow-Daten (MTTR, Incidents) | Signavio Process Insights → SAC |
| Dashboard | 1 SAC Story: Operational Health + Delivery Status | SAC |
| Portal | Einbettung in Build Work Zone (1 Seite) | Build Work Zone |
| Zielgruppe | Senior Management (Oliver Timm) | — |

**Bewusste Einschränkungen:**
- Kein Pendo, kein Gainsight, kein Qualtrics im MVP
- EKX erst wenn Datenzugriff geklärt ist
- Financials / Compliance vorerst nur als Link (nicht integriert)

### Phase 2 — Erweiterung (nach Abgabe, Juli–September 2026)

| Baustein | Voraussetzung |
|---|---|
| Pendo → Datasphere | Admin-Zugang + Data Sync API geklärt (Janine) |
| Qualtrics → Datasphere | API-Integration genehmigt (Janine) |
| Gainsight → Datasphere | Zugang + REST-API-Freigabe |
| EKX Report-Generierung | EKX-Datenzugriff auf Datasphere bestätigt |
| Weitere SAC Stories | Pendo + Qualtrics-Daten verfügbar |

---

## 4 — Offene Architektur-Entscheidungen

| Frage | Optionen | Status |
|---|---|---|
| **Build Work Zone: SAP-intern freigegeben für Signavio Engineering?** | Ja / Nein — Fallback: reines SAC-Portal | Janine fragen |
| **EKX: Zugriff auf Datasphere-Daten möglich?** | Live-Zugriff / nur statische SAP-Inhalte | Janine fragen |
| **Pendo-Integration: Data Sync oder REST API?** | Data Sync (einfacher) vs. REST API (flexibler) | Pendo-Owner klären |
| **Signavio Process Insights als primärer Ingestion-Layer?** | Ja (schnellster Weg für Jira/ServiceNow) vs. direkt Datasphere | Svitlana / Janine |
| **Collibra: Data Product „PX Foundation" direkt nutzbar für MVP?** | Ja — Qualtrics-Daten bereits als Gold-Datensatz vorhanden | Prüfen |

---

## 5 — Kritische Annahmen (noch nicht validiert)

1. Build Work Zone ist für Signavio Engineering-Nutzung freigegeben
2. EKX kann live auf Datasphere-Daten zugreifen (nicht nur statische Inhalte)
3. Pendo Data Sync → Datasphere ist technisch umsetzbar und genehmigt
4. Signavio-Adapter (Jira/ServiceNow) kann direkt für MVP-Stories in SAC genutzt werden — kein zusätzlicher Datasphere-Layer nötig für Phase 1

---

## 6 — Verhältnis zu bestehenden Initiativen

| Initiative | Verhältnis zum KPI-Hub |
|---|---|
| **One Voice (Lea Reib)** | Komplementär — One Voice = VoC/CX-Schicht; KPI-Hub = Engineering + Ops. Könnten dieselbe Build-Work-Zone-Instanz nutzen. |
| **COO Cross Team (Jens Hildenbrand)** | On Hold (Re-Org) — war konzeptionell ähnlich; KPI-Hub könnte Ergebnis aufgreifen |
| **DORA & QA Metrics (Stefan Popescu)** | Parallele Initiative — Abstimmung sinnvoll, ob Daten geteilt werden können |
| **Process Intelligence (Björn Wagner)** | Jira-Daten-Basis potentiell teilbar |
| **Product Excellence Portal** | Präzedenzfall für Portal-Ansatz — deprecated; Erweiterung oder Ablösung? |
