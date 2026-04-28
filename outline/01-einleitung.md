# Outline Kapitel 1 — Einleitung

**Kapitel:** 1 Einleitung  
**Geplanter Umfang:** 4 Seiten  
**Erstellt:** 28. April 2026  
**Status:** Entwurf

---

## Überblick und Argumentationslogik

Die Einleitung führt den Leser vom allgemeinen strukturellen Problem (Fragmentierung von BI-Landschaften in Unternehmen) über den konkreten Unternehmenskontext (SAP Signavio P&E) zur präzisen Forschungsfrage. Sie endet mit der Einordnung in die Wirtschaftsinformatik und einem Überblick über die Kapitelstruktur.

**Roter Faden:**  
Fragmentierung als strukturelles Problem (allgemein) → konkrete Ausprägung im SAP-Kontext → Lösungsrelevanz → WI-Einordnung → Forschungsfrage → Aufbau

---

## Forschungsfrage

**Hauptforschungsfrage:**

> Welcher Integrationsansatz eignet sich für die Realisierung eines KPI-Hubs in einer fragmentierten Enterprise-Systemlandschaft, und wie kann diese Entscheidung durch ein Mehrkriterien-Entscheidungsmodell methodisch fundiert werden?

**Teilfragen (strukturieren Kapitel 5–7):**

> TF1: Welche funktionalen und nicht-funktionalen Anforderungen stellt eine fragmentierte Enterprise-Systemlandschaft an einen KPI-Hub-Integrationsansatz?

> TF2: Wie kann ein Mehrkriterien-Entscheidungsmodell diese Anforderungen in eine begründete, nachvollziehbare Integrationsauswahl überführen?

**Begründung der Formulierung:**  
Die Hauptfrage ist zweiteilig, weil sie das Artefaktpaar der Arbeit abbildet: das Entscheidungsmodell (Modell-Artefakt) und den MVP (Instanz-Artefakt). Die Teilfragen markieren die Grenzlinie zwischen Anforderungsanalyse (Kap. 5) und Bewertungsmodell (Kap. 7). Die Frage ist beantwortbar, weil das Entscheidungsmodell operationalisierbar und der MVP evaluierbar ist.

**Abgrenzung (explizit zu nennen in 1.4):**  
- Nicht untersucht: andere Unternehmenskontexte außerhalb des SAP-Ökosystems  
- Nicht untersucht: vollständige Datenpipeline-Implementierung aller Quellsysteme im MVP  
- Nicht untersucht: langfristige Wartungsökonomie der gewählten Integrationslösung  
- Nicht untersucht: Change Management / Adoption beim Rollout

---

## Seitenverteilung

| Abschnitt | Seitenanteil | Begründung |
|-----------|-------------|------------|
| 1.1 Ausgangssituation und Problemstellung | ~1,2 Seiten | Kernaufgabe der Einleitung; Hänel-Anforderung verlangt Herleitung mit Studien |
| 1.2 Lösungsrelevanz und Motivation | ~0,8 Seiten | Brücke zum DSR-Relevance-Cycle; kürzer, da 1.1 das Fundament legt |
| 1.3 Einordnung in die Wirtschaftsinformatik | ~0,6 Seiten | Pflicht laut Hänel; kompakt, da Kap. 3 die Methodenbegründung ausführt |
| 1.4 Zielsetzung und Forschungsfrage | ~0,8 Seiten | Präzise Formulierung + Abgrenzung braucht etwas Raum |
| 1.5 Aufbau der Arbeit | ~0,4 Seiten | Standardabschnitt; knappe Auflistung der Kapitel |
| **Gesamt** | **~4,0 Seiten** | |

---

## 1.1 Ausgangssituation und Problemstellung (~1,2 Seiten)

**Argumentationsziel:** Der Leser versteht, dass die Fragmentierung von BI-Toollandschaften in Unternehmen ein wissenschaftlich dokumentiertes, strukturelles Problem ist — nicht ein Einzelfall bei SAP Signavio.

**Gliederungspunkte:**

1. **Einstieg: Wachsende Bedeutung datengestützter Entscheidungen im Enterprise-Kontext**  
   → Unternehmen investieren massiv in BI und Analytics; Entscheidungsqualität hängt zunehmend von Datenverfügbarkeit ab.  
   → Quelle: `larson2016` (BI/Analytics als strategische Unternehmensressource; Fragmentierung als Kernhindernis)

2. **Das strukturelle Problem: Historisch gewachsene, fragmentierte BI-Landschaften**  
   → Verschiedene BI-Subsysteme entstehen abteilungs- und systemweise, nicht nach einem zentralen Plan.  
   → Koexistenz heterogener BI-Systeme ist dokumentiertes Strukturproblem moderner Unternehmen.  
   → Quellen: `baars2008` (integriertes BI-Framework als Reaktion auf Fragmentierung), `larson2016` (Konsolidierung als offene Herausforderung)

3. **Konkretisierung: KPI-Heterogenität als direkte Folge**  
   → Wenn Subsysteme unkoordiniert wachsen, entstehen inkonsistente KPI-Definitionen und Messpraktiken.  
   → Quelle: `giovannoni2013` (drei Quellen von Definitionsheterogenität: Methodik-Schulen, historische Inkompatibilität, fehlende Governance)

4. **SSBI als Lösungsversuch — und seine Grenzen**  
   → Self-Service BI soll Datenzugang demokratisieren, scheitert aber an Datenqualitäts- und Governance-Problemen.  
   → Quelle: `lennerholt2018` (drei Hauptkategorien von SSBI-Implementierungsbarrieren)

5. **Einordnung in den Unternehmenskontext: SAP Signavio P&E**  
   → SAP Signavio Engineering operiert mit >10 heterogenen Metriken- und Dashboard-Systemen (SAC, ServiceNow, Jira, Gainsight, DORA, CircleCI usw.).  
   → Stakeholder berichten Fragmentierung, fehlende Vergleichbarkeit, mangelnde Auffindbarkeit.  
   → *Hinweis für Autor:* Konkrete Systemliste hier NICHT aufzählen — das gehört in Kap. 4. Nur abstrakt auf den Kontext verweisen.

**Übergang zu 1.2:** Die beschriebene Situation ist nicht nur ein technisches Versäumnis, sondern hat messbare negative Konsequenzen für Entscheidungsqualität und Effizienz. Diese Konsequenzen und der daraus folgende Handlungsbedarf werden im folgenden Abschnitt konkretisiert.

**Quellen für 1.1:** `larson2016`, `baars2008`, `giovannoni2013`, `lennerholt2018`

---

## 1.2 Lösungsrelevanz und Motivation (~0,8 Seiten)

**Argumentationsziel:** Der Leser erkennt die Diskrepanz zwischen dem Ist-Zustand (fragmentierte KPI-Landschaft, mangelnde Transparenz) und dem gewünschten Zustand (konsolidierter KPI-Hub), versteht die Hindernisse für diesen Übergang und sieht den aktuellen Handlungsbedarf.

**Gliederungspunkte:**

1. **Diskrepanz: Ist-Zustand vs. gewünschter Zustand**  
   → Ist: Daten verteilt auf silos, manueller Aufwand für Reports, inkonsistente Definitionen, Vertrauensverlust in Datenbasis.  
   → Soll: Zentraler Einstiegspunkt (KPI-Hub) mit konsistenten Definitionen, Near-Realtime-Daten, selbsterklärend navigierbar.  
   → *Hinweis:* Soll-Zustand nicht als konkrete Anforderungen ausführen — das gehört in Kap. 5. Hier nur die Zielrichtung skizzieren.

2. **Hindernisse: Warum ist die Konsolidierung schwierig?**  
   → Technisch: heterogene Datenmodelle, unterschiedliche APIs und Zugriffsrechte, Echtzeit-Anforderungen.  
   → Organisational: fehlende Governance, dezentrale Tool-Ownership, Akzeptanzprobleme bei Nutzern.  
   → Quelle: `lennerholt2018` (organisationale SSBI-Barrieren), `passlick2020` (Akzeptanzparadox: Betonung von Datenqualität kann Nutzungsabsicht senken)

3. **Negative Konsequenzen der aktuellen Situation**  
   → Ineffizienz: manueller Report-Aufwand bindet Kapazität (Slide-Decks, monatliche PDFs).  
   → Fehleranfälligkeit: unterschiedliche KPI-Definitionen führen zu divergierenden Interpretationen.  
   → Mangelnde Transparenz: Entscheidungen ohne verlässliche Datenbasis, Release-Blocker und Kapazitätsengpässe nicht sichtbar.  
   → Quelle: `baars2008` (BI-Fragmentierung als Managementsupport-Hindernis), `giovannoni2013` (Governance-Defizit als Ursache für Messinkonsistenz)

4. **Aktueller Handlungsbedarf**  
   → Technologisch: Reife von API-Integrationsansätzen, Föderations-Architekturen und Embedding-Paradigmen macht Konsolidierung heute machbar.  
   → Organisational: Wachsendes KPI-Hub-Konzept als Antwort auf "Single Pane of Glass"-Forderung.  
   → Forschungsseitig: Systematisches Entscheidungsmodell für die Integrationswahl fehlt in der Literatur — hier setzt die Arbeit an.  
   → Quelle: `larson2016` (Konsolidierung als offene Forschungsfrage)

**Übergang zu 1.3:** Die skizzierte Problemlage ist nicht nur unternehmenspraktisch relevant, sondern lässt sich in anerkannte Forschungsfelder der Wirtschaftsinformatik einordnen, was im folgenden Abschnitt geschieht.

**Quellen für 1.2:** `lennerholt2018`, `passlick2020`, `baars2008`, `giovannoni2013`, `larson2016`

---

## 1.3 Einordnung in die Wirtschaftsinformatik (~0,6 Seiten)

**Argumentationsziel:** Der Leser erkennt, dass diese Arbeit in einem etablierten WI-Forschungsfeld verortet ist und einen gestaltungsorientierten Beitrag innerhalb dieses Feldes leistet.

**Gliederungspunkte:**

1. **Forschungsfeld Enterprise Systems und Business Intelligence**  
   → Die Untersuchung ist im Teilgebiet Enterprise Information Systems verortet: Systeme zur Unterstützung unternehmensseitiger Entscheidungsprozesse durch strukturierte Daten.  
   → Subdisziplinen: BI-Architekturen, Performance Management, Data Integration.  
   → Quelle: `baars2008` (integrierte BI-Architekturen als WI-Forschungsgegenstand)

2. **Forschungsfeld Data Governance**  
   → Zugriffskontrolle über heterogene Quellsysteme hinweg ist ein Governance-Problem, das über reine IT-Architektur hinausgeht.  
   → Verweis auf Kap. 2.3 für die konzeptuelle Vertiefung.

3. **Forschungsfeld Entscheidungsunterstützung / MCDM in IS**  
   → Das Entscheidungsmodell als Artefakt gehört zum WI-Forschungsfeld der Entscheidungsunterstützungssysteme.  
   → Die Methodik (DSR) verortet die Arbeit in der gestaltungsorientierten Wirtschaftsinformatik.  
   → Quelle: `heinzl2024` (Doppelgesichtigkeit der WI: Seins- und Sollens-Wissenschaft; gestaltungsorientierte Forschung als eigenständige Form)

4. **Abgrenzung zum Forschungsfeld Informatik**  
   → Die Arbeit untersucht keine rein technischen Implementierungsdetails, sondern die methodisch fundierte Entscheidungsfindung zwischen Integrationsoptionen — eine WI-spezifische Fragestellung an der Schnittstelle von Technik und Organisation.

**Übergang zu 1.4:** Aus dieser Einordnung ergibt sich die präzise Zielsetzung der Arbeit und die zugrunde liegende Forschungsfrage.

**Quellen für 1.3:** `heinzl2024`, `baars2008`

---

## 1.4 Zielsetzung und Forschungsfrage (~0,8 Seiten)

**Argumentationsziel:** Der Leser kennt die präzise Forschungsfrage, das Forschungsziel (zwei Artefakte: Entscheidungsmodell + MVP), und weiß, was explizit nicht untersucht wird.

**Gliederungspunkte:**

1. **Zielsetzung**  
   → Ziel der Arbeit ist die Entwicklung eines Mehrkriterien-Entscheidungsmodells, das die Auswahl eines KPI-Hub-Integrationsansatzes in einer fragmentierten Enterprise-Systemlandschaft methodisch fundiert.  
   → Ergänzend wird ein MVP entwickelt, der den empfohlenen Ansatz unter Realbedingungen validiert.  
   → Die Arbeit leistet damit einen gestaltungsorientierten Beitrag: präskriptives Modellwissen (Ebene 2) + situierter Machbarkeitsnachweis (Ebene 1).  
   → *Hinweis:* Gregor & Hevner (2013)-Referenz hier NICHT ausführen — das steht in Kap. 3.1. Hier nur kurz andeuten.

2. **Hauptforschungsfrage**  
   → Welcher Integrationsansatz eignet sich für die Realisierung eines KPI-Hubs in einer fragmentierten Enterprise-Systemlandschaft, und wie kann diese Entscheidung durch ein Mehrkriterien-Entscheidungsmodell methodisch fundiert werden?

3. **Teilfragen**  
   → TF1: Welche funktionalen und nicht-funktionalen Anforderungen stellt eine fragmentierte Enterprise-Systemlandschaft an einen KPI-Hub-Integrationsansatz?  
   → TF2: Wie kann ein Mehrkriterien-Entscheidungsmodell diese Anforderungen in eine begründete, nachvollziehbare Integrationsauswahl überführen?

4. **Abgrenzung**  
   → Die Untersuchung beschränkt sich auf den SAP-Systemkontext von SAP Signavio P&E; eine Übertragung auf andere Unternehmensumgebungen ist nicht Gegenstand dieser Arbeit.  
   → Die MVP-Implementierung deckt exemplarisch einen Datenpfad ab; eine vollständige Produktivimplementierung aller Quellsysteme ist kein Forschungsziel.  
   → Langfristige Wartungsökonomie und Change-Management-Aspekte des Rollouts bleiben ausgeklammert.

**Übergang zu 1.5:** Die Beantwortung dieser Forschungsfrage erfolgt in einer strukturierten Abfolge von Kapiteln, die im folgenden Abschnitt skizziert wird.

**Quellen für 1.4:** keine externen Quellen erforderlich (Syntheseabschnitt)

---

## 1.5 Aufbau der Arbeit (~0,4 Seiten)

**Argumentationsziel:** Der Leser erhält eine mentale Landkarte der Arbeit und kann die Kapitelstruktur dem DSR-Prozessmodell zuordnen.

**Gliederungspunkte:**

1. **Struktur in einem Satz** — Die Arbeit folgt dem DSRM-Phasenmodell nach Peffers et al. (2007) und gliedert sich in zehn Kapitel.

2. **Kapitelübersicht (Tabellenform oder Fließtext — je nach Gestaltungspräferenz):**  
   - Kap. 2: Grundlagen und Stand der Forschung — konzeptionelles Fundament (KPI-Management, BI-Architektur, Integration, Data Governance, MCDM)  
   - Kap. 3: Methodik — Forschungsansatz (DSR), Literaturrecherche, Ergebniserwartung, Vorgehen  
   - Kap. 4: Ausgangssituation und Systemlandschaft — Ist-Analyse bei SAP Signavio P&E (DSRM Phase 1: Problemidentifikation)  
   - Kap. 5: Anforderungsanalyse — Erhebung und Priorisierung funktionaler und nicht-funktionaler Anforderungen (DSRM Phase 2: Zieldefinition)  
   - Kap. 6: Lösungsraum und Architektur-/Tooloptionen — Identifikation und Charakterisierung der Integrationsalternativen (DSRM Phase 3 vorbereiten)  
   - Kap. 7: Entscheidungs- und Bewertungsmodell — Aufbau und Anwendung des MCDM-Modells (DSRM Phase 3: Design & Entwicklung)  
   - Kap. 8: MVP — Design, Umsetzung und Validierung (DSRM Phase 4: Demonstration)  
   - Kap. 9: Ergebnisse und Diskussion — Evaluation des MVP und Sensitivitätsanalyse (DSRM Phase 5: Evaluation)  
   - Kap. 10: Fazit und Ausblick — Zusammenfassung, Limitationen, weiterführende Schritte (DSRM Phase 6: Kommunikation)

3. **Hinweis für Autor:** Kap. 3 kommt nach Kap. 2 im Dokument, erklärt aber methodisch, warum Kap. 4–10 so aufgebaut sind. Im Aufbauabschnitt kurz darauf hinweisen, dass Kap. 3 den methodischen Rahmen für alle nachfolgenden Kapitel legt.

**Quellen für 1.5:** `peffers2007` (nur bei expliziter DSRM-Nennung im Text, optional)

---

## Quellen-Mapping Gesamt

| Quelle | Abschnitt(e) | Verwendungszweck |
|--------|-------------|-----------------|
| `larson2016` | 1.1, 1.2 | BI-Fragmentierung als strukturelles Unternehmensproblem; Konsolidierung als offene Herausforderung |
| `baars2008` | 1.1, 1.2, 1.3 | Integrierte BI-Architektur; Fragmentierung als Managementsupport-Hindernis |
| `giovannoni2013` | 1.1, 1.2 | KPI-Definitionsheterogenität: drei Quellen, strukturelles Governance-Defizit |
| `lennerholt2018` | 1.1, 1.2 | SSBI-Implementierungsbarrieren (drei Kategorien); Lösungsrelevanz |
| `passlick2020` | 1.2 | Akzeptanzparadox bei SSBI; Nutzungsbereitschaft vs. Datenqualitätsbetonte Governance |
| `heinzl2024` | 1.3 | WI als gestaltungsorientierte Wissenschaft (Seins- vs. Sollens-Wissenschaft) |

**Noch nicht verplante Quellen (für Kap. 1 nicht benötigt):**  
`peffers2007`, `hevner2004`, `march1995`, `gregor2013` → gehören in Kap. 3  
`ferreirotley2009`, `parmenter2015`, `few2006`, `eckerson2010` → gehören in Kap. 2.1  
`fielding2000`, `kimball2013`, `hohpe2003`, `dehghani2022`, `nijkamp2009` → gehören in Kap. 2.2  
`ferraiolo2001`, `alhassan2016`, `tikkinenpiri2018`, `alaqrabi2013`, `ghazal2020` → gehören in Kap. 2.3  
`saaty1990`, `hwangyoon1981`, `velasquez2013`, `hanine2016`, `zaidan2015`, `pohl2010` → gehören in Kap. 2.4

---

## Schreibhinweise und Fallstricke

- **Keine internen SAP-Dokumente in Kap. 1** (Hänel-Anforderung). Alle Belege in 1.1 und 1.2 müssen extern und peer-reviewed sein.
- **Kein Vorwegnehmen von Kap. 4**: Die konkrete Systemliste (SAC, ServiceNow, Jira usw.) gehört in Kap. 4, nicht in 1.1. In 1.1 nur abstrakt vom "Unternehmenskontext bei SAP Signavio" sprechen.
- **Kein Vorwegnehmen von Kap. 3**: Die DSR-Methodenbegründung gehört in Kap. 3. In 1.4 nur kurz auf den gestaltungsorientierten Charakter hinweisen, ohne die volle Argumentation zu entfalten.
- **Keine Anforderungsliste in Kap. 1**: Konkrete Anforderungen (F01–F11) gehören in Kap. 5.
- **Zitationsregel**: `\vglcite[Seitenzahl]{key}` nach dem Satzende (nach Punkt). Seitenzahlen `XX` als Platzhalter bis zur finalen Literaturdurchsicht.
- **Forschungsfrage**: Die genaue Formulierung der Forschungsfrage darf nach Rückmeldung von Prof. Sachse (28. April 2026 Meeting) noch angepasst werden — das Outline bleibt als Planungsgrundlage gültig.
