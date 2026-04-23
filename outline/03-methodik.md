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

> **Hinweis:** Kann erst geschrieben werden, wenn die Literaturrecherche tatsächlich durchgeführt wurde.
> Inhalte fließen laufend in notes/LITERATURE.md ein — von dort hierher übertragen.

### Was rein muss (Checkliste für später)
- [ ] Verwendete Datenbanken (z.B. Google Scholar, ACM DL, Springer, EBSCO)
- [ ] Suchbegriffe (deutsch + englisch)
- [ ] Ein- und Ausschlusskriterien
- [ ] Anzahl gefundener / gescreenter / verwendeter Quellen (PRISMA-ähnlich)

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
