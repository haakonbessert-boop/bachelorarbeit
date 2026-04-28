# Kapitel 3 — Methodik

## 3.1 Forschungsansatz

**Hänel-Anforderung:** Welcher Forschungsansatz wird warum gewählt?

### Kernaussage
Design Science Research (DSR) ist die passende Methodik, weil das Ziel dieser Arbeit
die *Konstruktion* eines Artefakts ist — nicht Beschreibung oder Erklärung.

### Struktur der Argumentation

1. **Definition DSR** — Was ist DSR?
   - Quelle: Heinzl & Riedl (2024) für die WI-kontextgerechte Definition
   - Kerngedanke: Wissensgewinn durch Gestaltung eines IT-Artefakts

2. **Warum DSR für diese Arbeit?**
   - Ankerpunkt A (stärkste): Die zwei Artefakte sind Bewertungsmodell + MVP — Lehrbuchfall für DSR
     → Referenz: Hevner et al. (2004): "IT artifact" als Forschungsgegenstand
   - Ankerpunkt B: Realer industrieller Problemkontext (SAP Signavio P&E)
     → Stärkt die Relevanz-Achse nach Hevner (Rigor + Relevance)
   - Ankerpunkt C: Abgrenzung — warum *nicht* rein empirisch (z.B. nur Interviews)?
     → Ziel ist Gestaltung, nicht Beschreibung — empirische Methoden würden das Artefakt nicht liefern

3. **Rollenverteilung der Quellen**
   - Heinzl & Riedl (2024): Definition von DSR im WI-Kontext
   - Hevner et al. (2004): Kernkriterien (Rigor & Relevance, 7 Guidelines)
   - Peffers et al. (2007): Prozessmodell (führt direkt zu 3.4 Vorgehen im Überblick)

### Offene Fragen / zu klären
- [ ] Wie tief soll die DSR-Erklärung gehen? (1 Absatz Definition reicht vermutlich)
- [ ] Soll die Abgrenzung zu empirischen Methoden explizit als eigener Absatz, oder nur ein Satz?

---

## 3.2 Literaturrecherche

**Hänel-Anforderung:** Rechercheprozess dokumentieren (Suche, Auswertung, Analyse, Interpretation)

**Methodik-Grundlage:** vom Brocke et al. (2009) 5-Phasen-Rahmen + Webster & Watson (2002) concept-centric review.

**Ziel des Abschnitts im Text:** Reproduzierbarer Nachweis, dass die Literaturbasis wissenschaftlich fundiert und nicht willkürlich zusammengestellt ist. Hänel verlangt explizite Dokumentation — kein beschönigender Überblick.

---

### Struktur des Abschnitts (Reihenfolge im LaTeX-Text)

1. **Einleitungssatz:** Warum systematische Suche? Rigor Cycle nach Hevner; Dokumentation nach vom Brocke (2009) und Webster & Watson (2002).
2. **Themenbereiche / Suchfelder** (tabellarisch)
3. **Datenbanken**
4. **Suchstrings** (themenspezifisch)
5. **Ein- und Ausschlusskriterien** (als Tabelle)
6. **Trefferauswertung / PRISMA-Flowchart** (Zahlen nach Durchführung nachtragen)
7. **Kurze Synthese:** Wie wurden Treffer zu Themenblöcken geordnet? Was ist der Stand der Forschung in jedem Block?

---

### Themenbereiche (Suchfelder)

| # | Themenblock | Warum relevant | Kapitel |
|---|-------------|----------------|---------|
| T1 | Enterprise BI-Integration & KPI-Management | Kernthema: fragmentierte Systemlandschaft, zentrale KPI-Versorgung | 2.1, 2.2 |
| T2 | Integrationsparadigmen (ETL, EAI/EIP, REST API, Embedded Analytics) | Lösungsraum für Kap. 6 | 2.2, 6 |
| T3 | RBAC in Enterprise-Systemen | Kernanforderung aus Stakeholder-Analyse | 2.3, 5 |
| T4 | Mehrkriterien-Entscheidungsmethoden (AHP, TOPSIS, Nutzwertanalyse) | Methodische Basis für Bewertungsmodell Kap. 7 | 2.4, 7 |
| T5 | Design Science Research (Methodik) | Forschungsrahmen — bereits gut abgedeckt | 3 |

---

### Datenbanken

Primäre Datenbanken (Peer-reviewed, IS/WI-relevant):

| Datenbank | URL | Abdeckung |
|-----------|-----|-----------|
| **ACM Digital Library** | dl.acm.org | Informatik, IS, Software Engineering — besonders stark für T2, T3, T4 |
| **IEEE Xplore** | ieeexplore.ieee.org | Technische Informatik, Systems Engineering — stark für T2, T3 |
| **Springer Link** | link.springer.com | WI, BWL, IS — gut für deutschsprachige Quellen (T1, T4) |
| **EBSCO Business Source Complete** | Hochschulzugang BA Dresden | Management IS, BI, betriebswirtschaftliche Perspektive (T1) |
| **Google Scholar** | scholar.google.com | Breit, Vorwärts-/Rückwärtssuche, Graufiteratur; ergänzend, nicht primär |

Ergänzende Quellen (nicht blind primär suchen):

| Datenbank / Quelle | Zweck |
|--------------------|-------|
| **Scopus** | Cross-check Trefferqualität, Zitationsanalyse |
| **WISO** | Deutschsprachige WI-Journals (Wirtschaftsinformatik, BISE) |
| **dblp** | Technische Suche für ACM/IEEE-Konferenzen (ERP-Integration) |
| **Snowballing** | Rückwärts (Literaturlisten) + Vorwärts (Google Scholar "Cited by") — nach Webster & Watson (2002) |

---

### Suchstrings (themenspezifisch)

Notation: `AND`, `OR`, `*` (Trunkierung), `"..."` (Phrase). Strings sind für ACM DL / IEEE Xplore optimiert; für Springer ggf. vereinfachen.

#### T1 — Enterprise BI-Integration & KPI-Management

```
("KPI" OR "key performance indicator" OR "business intelligence") AND
("enterprise integration" OR "fragmented" OR "dashboard consolidation" OR "BI landscape")

("KPI management" OR "KPI hub" OR "KPI dashboard") AND
("enterprise system" OR "information system" OR "SAP")

"business intelligence fragmentation" OR "BI fragmentation"

("KPI" OR "performance measurement") AND "enterprise information system*"
```

**Deutsch (Springer / WISO):**
```
("KPI" OR "Kennzahl") AND ("Enterprise" OR "Unternehmens-BI") AND ("Integration" OR "Fragmentierung")
```

#### T2 — Integrationsparadigmen

```
("ETL" OR "extract transform load") AND ("business intelligence" OR "data warehouse" OR "enterprise")

("enterprise application integration" OR "EAI") AND ("integration pattern*" OR "message broker")

("REST API" OR "RESTful") AND ("enterprise integration" OR "data integration")

"embedded analytics" AND ("enterprise system*" OR "SAP" OR "ERP")

("data mesh" OR "data fabric") AND "enterprise analytics"

("integration paradigm*" OR "integration approach*") AND
("enterprise system*" OR "ERP" OR "business intelligence")
```

#### T3 — RBAC in Enterprise-Systemen

```
("role-based access control" OR "RBAC") AND
("business intelligence" OR "analytics" OR "dashboard" OR "enterprise")

("RBAC" OR "access control") AND ("data governance" OR "information governance")

("role-based access control" OR "RBAC") AND ("ERP" OR "SAP" OR "enterprise system*")

"attribute-based access control" AND "enterprise analytics"
```

#### T4 — Mehrkriterien-Entscheidungsmethoden

```
("analytic hierarchy process" OR "AHP") AND
("software selection" OR "tool selection" OR "IT selection" OR "enterprise system")

("TOPSIS" OR "technique for order preference") AND
("information system*" OR "software engineering" OR "IT evaluation")

("multi-criteria decision" OR "MCDM" OR "multiple criteria") AND
("enterprise system selection" OR "IT architecture" OR "integration approach")

"Nutzwertanalyse" AND ("Softwareauswahl" OR "IT-Entscheidung")

("weighted scoring" OR "scoring model") AND
("information system*" OR "enterprise software" OR "tool selection")
```

#### T5 — Design Science Research (ergänzend / Anschlussliteratur)

```
"design science research" AND "information system*"
("DSR" OR "design science") AND ("evaluation" OR "artifact" OR "artefact")
```

---

### Ein- und Ausschlusskriterien

| Kriterium | Einschluss | Ausschluss |
|-----------|-----------|------------|
| **Sprache** | Deutsch, Englisch | Alle anderen Sprachen |
| **Erscheinungsjahr** | 2000–2026 (Ausnahmen: Grundlagenwerke älter als 2000, z.B. Saaty 1990, Kimball/Ross) | Vor 1990 (ohne explizite Begründung) |
| **Publikationstyp** | Peer-reviewed Journals, Konferenzbeiträge (ACM, IEEE, ECIS, ICIS, DESRIST), Lehrbücher einschlägiger Verlage | Blog-Beiträge, Vendor-Whitepapers, interne Unternehmensdokumente (außer als Primärquellen für Kap. 4) |
| **Thematische Relevanz** | Direkte inhaltliche Abdeckung eines der Themenblöcke T1–T5 | Rein domänenfremde Studien (z.B. medizinische BI-Systeme ohne IS-Übertragbarkeit) |
| **Zugänglichkeit** | Volltext zugänglich (Hochschulzugang BA Dresden, Open Access, Bibliothek) | Nur Abstract verfügbar, kein Volltext beschaffbar |
| **Qualitätsmindestanforderung** | Mindestens Konferenzbeitrag (ACM/IEEE-Track); Journals bevorzugt | Nicht-begutachtete Preprints (ausgenommen arXiv-Preprints mit nachgewiesener Zitationsqualität) |

**Begründung der Zeitraumgrenze:** Das Feld der Enterprise-Integration und BI hat sich seit 2000 grundlegend verändert (Cloud, REST, Data Mesh). Ältere Grundlagenwerke (Saaty 1990: AHP; Kimball/Ross 1996/2013: Data Warehousing; Ferraiolo et al. 2001: RBAC) werden als Seminalwerke explizit einbezogen.

---

### Trefferauswertung (PRISMA-analog)

**Prozess (nach vom Brocke 2009, Phasen 3–4):**

1. **Datenbanksuche:** Suchstrings in alle Primärdatenbanken eingeben → Trefferanzahl je Datenbank und Suchstring notieren
2. **Deduplizierung:** Doppeltreffer über Datenbanken hinweg entfernen
3. **Title/Abstract-Screening:** Titel und Abstract gegen Ein-/Ausschlusskriterien prüfen
4. **Volltext-Screening:** Verbliebene Treffer im Volltext auf Relevanz und Qualität prüfen
5. **Einschluss:** Finale Quellen in `notes/LITERATURE.md` eintragen (BibTeX-Key + Analyse)
6. **Snowballing:** Rückwärts (Literaturlisten der eingeschlossenen Quellen) + Vorwärts (Google Scholar "Cited by") für zentrale Quellen

**Tabelle für den Text (Zahlen nach Durchführung nachtragen):**

| Stufe | Treffer |
|-------|---------|
| Datenbanksuche gesamt (roh) | XX |
| Nach Deduplizierung | XX |
| Nach Title/Abstract-Screening | XX |
| Nach Volltext-Screening | XX |
| + Snowballing | XX |
| **Endgültig eingeschlossen** | **XX** |

**Hinweis für Autor:** Die Gesamtzahl der eingeschlossenen Quellen liegt erfahrungsgemäß bei 40–60 für eine BA-Arbeit dieser Komplexität. Hänel fordert ~45 Quellen; das ist realistisch erreichbar.

---

### Argumentation im Text (Aufbau der Absätze)

**Absatz 1 — Begründung und methodischer Rahmen:**
Warum systematische Suche notwendig ist (Rigor Cycle nach Hevner); Verweis auf vom Brocke (2009) und Webster & Watson (2002) als methodische Grundlage.

**Absatz 2 — Themenbereiche:**
Die Recherche deckt fünf Themenblöcke ab (T1–T5). Jeder Block ist einem oder mehreren Kapiteln direkt zugeordnet. → kurze Nennung der fünf Blöcke, tabellarisch oder als Aufzählung.

**Absatz 3 — Datenbanken:**
Verwendete Primärdatenbanken nennen (ACM DL, IEEE Xplore, Springer, EBSCO); Begründung: IS/WI-Abdeckung. Snowballing ergänzend nach Webster & Watson (2002).

**Absatz 4 — Suchstrings:**
Exemplarisch 2–3 repräsentative Strings nennen (nicht alle — würde den Text aufblähen). Vollständige Strings in Anhang verweisen oder in einer kompakten Tabelle.

**Absatz 5 — Kriterien:**
Ein-/Ausschlusskriterien als Tabelle. Zeitraumgrenze begründen.

**Absatz 6 — Ergebnis:**
PRISMA-Flowchart oder kompakte Tabelle mit Trefferanzahlen. Abschlusssatz: Wie viele Quellen wurden eingeschlossen, wie verteilen sie sich auf die Themenblöcke?

---

### Quellen für diesen Abschnitt

| Quelle | Funktion in 3.2 |
|--------|----------------|
| vom Brocke et al. (2009) `vombrocke2009` | Methodischer Rahmen (5 Phasen, Dokumentationspflicht) |
| Webster & Watson (2002) `webster2002` | Strukturierungslogik (concept-centric, Snowballing) |

---

### Offene Fragen / Abhängigkeiten

- [ ] **Blocker aufgelöst durch:** Suchstrings und Kriterien sind jetzt definiert — Recherche kann beginnen
- [ ] **Nächster Schritt:** Suche in ACM DL, IEEE Xplore, Springer, EBSCO mit den Strings oben durchführen; Treffer in `notes/LITERATURE.md` dokumentieren
- [ ] **Zahlen nachtragen:** XX-Platzhalter in PRISMA-Tabelle nach Durchführung mit echten Werten ersetzen
- [ ] Soll die vollständige Suchstring-Tabelle in den Anhang oder inline im Text? (Empfehlung: kompakter Ausschnitt inline, Vollständige Liste als Anhang A — spart Platz im Methodikteil)
- [ ] Ist ein grafischer PRISMA-Flowchart (TikZ) gewünscht oder reicht die Tabelle? (Empfehlung: Tabelle reicht für BA — Flowchart wäre Overkill, kann aber leicht nachgerüstet werden)

---

## 3.3 Ergebniserwartung

**Hänel-Anforderung:** Was soll aus der Methodik herauskommen? Wie wird Zielerreichung gemessen?

> **Vorbehalt:** Die Artefakte sind zum Zeitpunkt dieser Outline noch nicht erstellt. Dieser Abschnitt
> formuliert eine *vorläufige Ergebniserwartung* auf Basis des Problemverständnisses und der
> methodischen Rahmenbedingungen. Die konkreten Inhalte werden nach Abschluss der Designphasen
> (Kap. 6–8) präzisiert.

### Kernaussage

Diese Untersuchung erwartet zwei komplementäre Artefakte: ein Mehrkriterien-Bewertungsmodell
(Artefakt-Typ *Modell* nach March & Smith 1995) zur strukturierten Auswahl einer Integrationslösung
sowie einen MVP/PoC (*Instanz* nach March & Smith 1995) zur operativen Validierung des
bevorzugten Ansatzes — bewertet anhand ihrer Abdeckung der erhobenen Anforderungen.

### Struktur der Argumentation

1. **Artefakt-Typen einordnen**
   - Ankerpunkt: March & Smith (1995) unterscheiden vier Artefakttypen (Konstrukt, Modell, Methode, Instanz)
   - Artefakt 1 (Bewertungsmodell) = Typ *Modell* (Level-2): abstrahiert den Lösungsraum in eine
     vergleichbare Struktur, ohne selbst eine konkrete Implementierung zu sein
   - Artefakt 2 (MVP/PoC) = Typ *Instanz* (Level-1): konkrete, lauffähige Realisierung eines
     Integrationsansatzes in der Zielumgebung
   - Hinweis für Text: Die Typisierung begründet, warum beide Artefakte methodisch notwendig sind —
     das Modell liefert die Entscheidungsgrundlage, die Instanz den Machbarkeitsnachweis

2. **Artefakt 1: Mehrkriterien-Bewertungsmodell (vorläufige Erwartung)**
   - Lösungsraum: ca. 5–7 Tool-Kandidaten (u.a. SAP Analytics Cloud, Build Work Zone, Drittanbieter)
   - Kriterienkatalog in Rohform: Machbarkeit/SAP-Freigabe, RBAC-Unterstützung, Integrationsaufwand,
     Daten-Aktualität (Freshness), lizenzrechtliche Rahmenbedingungen
   - Gewichtungsmethodik offen: AHP, Nutzwertanalyse oder TOPSIS — wird in Kap. 6 entschieden
     (Methodenbenennung nach Sachse als Ausgangspunkt)
   - Erwartetes Ergebnis: eine priorisierte Rangliste der Integrationsansätze mit nachvollziehbarer
     Begründung, die als Entscheidungsvorlage für das Praxisunternehmen dient

3. **Artefakt 2: MVP / PoC (vorläufige Erwartung)**
   - Quellsysteme faktisch belegt: Jira (Entwicklungsmetriken) + ServiceNow (ITSM-Kennzahlen)
   - Zielsystem: offen — Build Work Zone als wahrscheinlichste Option, SAP Analytics Cloud als
     Alternative; wird in Kap. 7/8 festgelegt
   - Erwartetes Ergebnis: ein funktionsfähiger Prototyp, der mindestens einen end-to-end
     Datenpfad (Quellsystem → KPI-Hub → Darstellung) demonstriert

4. **Evaluationslogik: FEDS-Framework (Venable 2016)**
   - Ankerpunkt: Venable et al. (2016) FEDS-Framework strukturiert die Evaluationsstrategie
     für DSR-Artefakte entlang zweier Dimensionen (formativ/summativ × artifizell/naturalistisch)
   - Artefakt 1 (Modell): *formative* Evaluation — begleitende Überprüfung während des
     Designprozesses (z.B. Expertenreview des Kriterienkatalogs)
   - Artefakt 2 (MVP): *naturalistisch-summative* Evaluation — abschließende Bewertung im
     realen Nutzungskontext (SAP-Praxisumgebung)
   - Hinweis für Text: FEDS rechtfertigt, warum unterschiedliche Evaluationsformen für die
     zwei Artefakte angemessen sind

5. **Zentrales Evaluationskriterium: Anforderungsabdeckung**
   - Ankerpunkt: Cleven et al. (2009) — Anforderungsabdeckung als primäres DSR-Erfolgskriterium
   - Operationalisierung: Abgleich der Artefakt-Leistung mit dem in Kap. 5 erhobenen
     Anforderungskatalog (F01–F11, NF01–NF06)
   - Sekundärkriterien (vorläufig): Nachvollziehbarkeit der Modellentscheidungen,
     technische Machbarkeit im SAP-Ökosystem

### Rollenverteilung der Quellen

| Quelle | Funktion in 3.3 |
|---|---|
| March & Smith (1995) | Artefakt-Typisierung (Modell vs. Instanz) |
| Venable et al. (2016) | FEDS-Framework — Evaluationsstrategie |
| Cleven et al. (2009) | Evaluationskriterium (Anforderungsabdeckung) |
| Sachse (intern) | Methodenbenennung für Gewichtungsverfahren (AHP / NWA / TOPSIS) |

### Offene Fragen / zu klären

- [ ] Welches Gewichtungsverfahren wird gewählt? (AHP vs. Nutzwertanalyse vs. TOPSIS) — Entscheidung in Kap. 6
- [ ] Zielsystem MVP: Build Work Zone oder SAP Analytics Cloud? — offen bis Kap. 7
- [ ] Soll die Typisierung nach March & Smith in einem eigenen Absatz erklärt werden, oder nur kurz als Klammer?
- [ ] Wie detailliert soll der Kriterienkatalog hier antizipiert werden? (Kap. 6 liefert das Vollbild)
- [ ] Reicht ein Verweis auf FEDS als Evaluationsrahmen, oder soll die Logik hier vollständig hergeleitet werden?

---

## 3.4 Vorgehen im Überblick

**Hänel-Anforderung:** Wie erfolgt die Untersuchung? Überblick über die Phasen.

> **Hinweis:** Direkte Ableitung aus dem Zeitplan. Eng verzahnt mit Peffers 2007 (DSRM-Phasen).

### Phasen-Mapping: DSRM → diese Arbeit

| DSRM-Phase (Peffers) | Entsprechung in dieser Arbeit | Kapitel |
|---|---|---|
| Problem Identification | Ist-Analyse, Stakeholder-Interviews | Kap. 4 + 5 |
| Define Objectives | Anforderungskatalog (F01–F11, NF01–NF06) | Kap. 5 |
| Design & Development | Scoring-Modell + MVP-Konzept | Kap. 6 + 7 + 8 |
| Demonstration | MVP-Umsetzung & Validierung | Kap. 8 |
| Evaluation | Bewertung gegen Anforderungen | Kap. 9 |
| Communication | Diese Arbeit | — |
