# Kapitel 2 — Grundlagen und Stand der Forschung

**Hänel-Anforderung:** Defizite bestehender Ansätze fundiert herausarbeiten (Literatur, keine
internen Docs/Blogs); alle Aussagen belegen — auch allgemein Bekanntes.

**Umfang-Zielwert:** 9 Seiten (laut THESIS_STATUS.md)

**Funktion im Gesamtgefüge:** Kapitel 2 legt das theoretische Fundament, auf das alle späteren
Kapitel aufbauen. Es klärt die Kernbegriffe (KPI, BI, Integration, RBAC, MCDM), zeigt den
Stand der Forschung in den vier relevanten Teilfeldern und endet mit einem Syntheseabschnitt
(2.5), der die Defizite bestehender Ansätze herausarbeitet — und damit unmittelbar begründet,
warum die vorliegende Arbeit ein neues Entscheidungsmodell benötigt.

**Überleitung zu Kapitel 3:** Am Ende von 2.5 wird das so aufgebaute Defizitbild in eine
Forschungslücke überführt: Die Literatur liefert einzelne Bausteine (MCDM-Methoden, RBAC-Modelle,
BI-Integrationsframeworks), aber kein integriertes Entscheidungsmodell, das alle drei Dimensionen
für den Kontext einer fragmentierten Enterprise-BI-Landschaft zusammenführt. Daraus folgt die
Methodenwahl (DSR, Kap. 3): Wenn die Lücke ein fehlendes Artefakt ist, ist Design Science
Research die passende Antwort.

---

## 2.1 KPI-Management und Business Intelligence

**Argumentationsziel:** Der Leser soll KPIs, BI und Dashboards präzise unterscheiden können
und verstehen, warum ein KPI-Hub konzeptuell mehr ist als ein weiteres Dashboard. Die
Begriffsdefinitionen in diesem Abschnitt sind die terminologische Grundlage für alle folgenden
Kapitel — insbesondere für die Anforderungsanalyse (Kap. 5) und das Entscheidungsmodell (Kap. 7).

### Gliederungspunkte

1. **KPI-Definition und Abgrenzung:** KPI vs. KRI vs. PI — Ferreira & Otley (2009) liefern die
   akademisch präzise Unterscheidung; Parmenter (2015) ergänzt praxisorientiert die "10 Schritte".
2. **Dashboard-Typen:** Few (2006) definiert Dashboards als "visual display of the most important
   information ... on a single screen"; Eckerson (2010) differenziert strategische, taktische und
   operative Dashboards — Letztere entsprechen dem KPI-Hub-Anwendungsfall.
3. **Business Intelligence im Enterprise-Kontext:** BI als organisatorischer Infrastrukturbegriff
   (Larson & Chang 2016 — zeigt BI-Fragmentierung als strukturelles Problem).
4. **Self-Service BI:** SSBI als Paradigma (Michalczyk et al. 2020 — State-of-the-art-Überblick);
   Implementierungsherausforderungen (Lennerholt et al. 2018); Akzeptanzproblem (Passlick et al. 2020).
5. **KPI-Hub als Konzept:** Einordnung des KPI-Hub als föderiertes Performance-Dashboard —
   verbindet die Dashboard-Definition (Few) mit dem Enterprise-BI-Rahmen (Eckerson, Larson).

### Quellen

| BibTeX-Key | Funktion |
|---|---|
| `ferreirotley2009` | Primärdefinition KPI / PMS-Framework |
| `parmenter2015` | Praxisperspektive KPI-Implementierung |
| `few2006` | Dashboard-Definition (Primärquelle) |
| `eckerson2010` | Dashboard-Typen, Enterprise-Performance-Management |
| `larson2016` | BI-Fragmentierung als strukturelles Unternehmensproblem |
| `michalczyk2020` | SSBI State of the Art |
| `lennerholt2018` | SSBI-Implementierungsherausforderungen |
| `passlick2020` | SSBI-Akzeptanz und Nutzungsabsicht |

### Übergang

Der Abschnitt schließt mit der Feststellung, dass ein KPI-Hub technisch auf Datenintegration
über mehrere Quellsysteme angewiesen ist — was die Frage aufwirft, welche Integrationsparadigmen
dafür geeignet sind. Überleitung: "Damit ein KPI-Hub die beschriebenen Dashboardtypen bedienen
kann, müssen heterogene Datenquellen angebunden werden. Die dafür verfügbaren
Enterprise-Integrationsparadigmen werden im folgenden Abschnitt systematisiert."

### Seitenumfang

ca. 2,0–2,5 Seiten

---

## 2.2 Enterprise-Systemintegration

**Status: VOLLSTÄNDIG GESCHRIEBEN (27.04.2026)**

**Argumentationsziel:** Der Leser soll die vier Integrationsparadigmen — ETL/DWH,
Messaging, REST-API und Embedded Analytics (EA) — in ihrer konzeptuellen Logik und ihren
Kompromissen kennen und verstehen, warum für den KPI-Hub-Kontext nicht ein einzelnes
Paradigma ausreicht. Der Abschnitt liefert die begriffliche Grundlage für den Lösungsraum
in Kap. 6 und begründet die Kriterienauswahl im Entscheidungsmodell (Kap. 7).

### Gliederungspunkte (implementiert)

1. **ETL und Data Warehouse als Integrationsparadigma:** Kimball & Ross (2013) — Star Schema,
   Bus-Architektur, ETL-Prozess; Batch-Charakter und Schema-Management als strukturelle
   Einschränkung für operative KPI-Dashboards.
2. **Messaging-basierte Integration:** Enterprise Integration Patterns (Hohpe & Woolf 2003) —
   konzeptuelle Grundlage; Batch vs. Event-getriebene Systeme; Entkopplung als struktureller
   Vorteil gegenüber ETL.
3. **REST-API-basierte Integration:** Fielding (2000) als Primärquelle für die sechs
   REST-Constraints; Pull-Modell und Verfügbarkeitsabhängigkeit im KPI-Hub-Kontext.
4. **Embedded Analytics (EA) als viertes Paradigma:** Nijkamp et al. (2009) als akademische
   Primärquelle (BTW 2009, GI-Fachbereich DBIS, peer-reviewed). EA bezeichnet die kontextuelle
   Einbettung analytischer Inhalte in die Benutzeroberfläche einer Fachanwendung — Verlagerung
   des Integrationspunkts von der Daten- auf die Präsentationsebene. Im KPI-Hub-Kontext:
   SAC-Dashboards eingebettet in Build Work Zone als "Single Pane of Glass". Entspricht
   konzeptuell dem Federation-Begriff: Daten verbleiben im Quellsystem, nur die Ansicht wird
   integriert. Academisch eigenständig, kein Sonderfall von REST-API-Integration.
5. **Integrationsrahmen und Defizitdiagnose:** Baars & Kemper (2008) — fragmentierte Koexistenz
   separater BI-Systeme als fundamentales Strukturproblem; kein einzelnes Paradigma löst es
   allein. Brücke zu 2.5.

> **[ENTSCHEIDUNG KAP2-E1] Embedding-Paradigma in 2.2 — ABGESCHLOSSEN**
>
> - **Status:** Option A vollständig umgesetzt (27.04.2026). Kap. 2.2 geschrieben und
>   qualitätsgesichert. Keine offene Frage mehr.
> - **Entscheidung (Option A):** `nijkamp2009` (BTW 2009, GI-Fachbereich DBIS, peer-reviewed)
>   als akademisch zitierfähige Primärquelle für EA. EA als viertes eigenständiges
>   Integrationsparadigma behandelt. Acronyms ergänzt: `ea`, `rest`, `eip`.
> - **DSR-Begründung:** EA ist für das Entscheidungsmodell (Kap. 7) unverzichtbar, weil der
>   Praxiskontext — SAP Build Work Zone als Portal-Layer, SAC-Stories via Live-Embedding —
>   genau diesem Paradigma entspricht (vgl. KPI_HUB_KONZEPT.md, Schicht 3). Ohne EA als
>   eigenständige Option würde Kap. 7 ein reales Architekturmuster nicht abbilden können.
>   Die Kriterienmatrix in Kap. 7 muss EA als vollwertige Alternative neben ETL/DWH,
>   Messaging und REST enthalten.
> - **Nicht gewählt — Option B** (Sonderfall von REST): EA operiert auf Präsentationsebene,
>   nicht auf Datenübertragungsebene — konzeptuell inkompatibel mit REST-Integration.
> - **Nicht gewählt — Option C** (streichen): Würde den Praxiskontext (Build Work Zone +
>   SAC-Embedding) aus dem theoretischen Rahmen herausnehmen und damit die Brücke von
>   Kap. 2 zu Kap. 6 schwächen.

### Quellen (implementiert)

| BibTeX-Key | Funktion |
|---|---|
| `kimball2013` | ETL / DWH-Paradigma (Star Schema, Bus-Architektur) |
| `hohpe2003` | Enterprise Integration Patterns / Messaging |
| `fielding2000` | REST-Architekturstil (Primärquelle, sechs Constraints) |
| `nijkamp2009` | Embedded Analytics — Primärquelle (BTW 2009, peer-reviewed) |
| `baars2008` | Integriertes BI-Framework; Fragmentierung als strukturelles Problem |

**Hinweis:** `dehghani2022` (Data Mesh) wurde in der Implementierung nicht verwendet.
EA/Nijkamp2009 übernimmt die konzeptuelle Rolle der Föderationsebene präziser und
quellengestützt. Dehghani bleibt als optionale Ergänzungsquelle für Kap. 6 reserviert.

### Übergang (implementiert)

"Die skizzierten Integrationsparadigmen setzen voraus, dass Datenzugriffsrechte konsistent
über Quellsysteme hinweg durchgesetzt werden können. Dies erfordert ein explizites
Data-Governance- und Zugriffskontrollmodell, das im folgenden Abschnitt entwickelt wird."

### Seitenumfang

ca. 2,5 Seiten (mit EA-Paradigma und Vergleichstabelle; implementiert)

---

## 2.3 Data Governance und Zugriffskontrolle

**Argumentationsziel:** Der Leser soll das RBAC-Modell als konzeptuelle Grundlage für
rollengebundene Datensichtbarkeit im Enterprise-Kontext kennen und verstehen, dass RBAC
in heterogenen Multi-System-Umgebungen (wie dem KPI-Hub) eine zusätzliche
Harmonisierungsschicht benötigt. Außerdem sollen DSGVO-Anforderungen als nicht-funktionale
Randbedingungen etabliert werden. Dieser Abschnitt liefert die Grundlage für die
RBAC-Anforderungen in Kap. 5.

### Gliederungspunkte

1. **Data Governance als Konzept:** Alhassan et al. (2016) — Definition, Aktivitäten
   (Datenpolitik, Datenqualität, Compliance); Data Governance als organisatorischer Rahmen.
2. **RBAC-Referenzmodell:** Ferraiolo et al. (2001) — NIST-Standard; Core RBAC, hierarchisches
   RBAC, Separation of Duty. Formale Definition: Rollen, Berechtigungen, Sessions.
3. **RBAC in BI-Cloud-Umgebungen:** Al-Aqrabi et al. (2013) — rollenbasierte Zugriffskontrolle
   für BI-Systeme in Cloud-Infrastrukturen; mehrschichtige Zugriffssteuerung.
4. **RBAC in heterogenen Multi-Domain-Systemen:** Ghazal et al. (2020) — semantische
   Rollenkorrespondenz für domänenübergreifende Harmonisierung; direkt anwendbar auf
   KPI-Hub mit mehreren Quellsystemen (SAC, Jira, ServiceNow).
5. **DSGVO als regulatorische Rahmenbedingung:** Tikkinen-Piri et al. (2018) — Anforderungen
   an personenbezogene Datenverarbeitung in Enterprise-Systemen; Privacy by Design als
   Architekturprinzip.

### Quellen

| BibTeX-Key | Funktion |
|---|---|
| `alhassan2016` | Data Governance Konzept und Aktivitätskatalog |
| `ferraiolo2001` | RBAC-Referenzmodell (NIST-Standard, Primärquelle) |
| `alaqrabi2013` | RBAC in BI-Cloud-Kontext |
| `ghazal2020` | RBAC-Harmonisierung in heterogenen Multi-System-Umgebungen |
| `tikkinenpiri2018` | DSGVO-Compliance-Anforderungen |

### Übergang

Der Abschnitt schließt mit der Feststellung, dass Governance-Fragen und RBAC-Anforderungen
die Entscheidung zwischen Integrationsansätzen mitbestimmen — ein Kriterium, das in die
Entscheidungsmethodik einfließen muss. Überleitung: "Welche formalen Methoden geeignet
sind, um eine solche Mehrkriterien-Entscheidung systematisch zu treffen, zeigt der
folgende Abschnitt."

### Seitenumfang

ca. 1,5–2,0 Seiten

---

## 2.4 Entscheidungsmethoden im Software Engineering

**Argumentationsziel:** Der Leser soll die drei relevanten MCDM-Methoden (Nutzwertanalyse,
AHP, TOPSIS) in ihrer Logik und ihren Stärken/Schwächen kennen und die theoretische Grundlage
für die Methodenwahl in Kap. 7 nachvollziehen können. Dieser Abschnitt erfüllt die explizite
Anforderung von Sachse (21.04.2026): "Methoden aus dem Software Requirement Engineering
heranziehen." Er bildet die theoretische Brücke zu Kap. 7 (Bewertungsmodell).

### Gliederungspunkte

1. **Anforderungspriorisierung als RE-Methode:** Pohl (2010) — MoSCoW-Methode und
   Nutzwertanalyse als etablierte RE-Verfahren zur Priorisierung bei mehreren konkurrierenden
   Anforderungen; Nutzwertanalyse als einfachstes Mehrkriterienverfahren.
2. **Multi-Criteria Decision Making (MCDM) — Überblick:** Velasquez & Hester (2013) —
   systematischer Methodenvergleich (AHP, TOPSIS, ELECTRE, PROMETHEE u.a.); Kriterien
   für die Methodenwahl (Datenbedarf, Transparenz, Rechenaufwand).
3. **AHP — Analytic Hierarchy Process:** Saaty (1990) — paarweise Vergleiche, Prioritätsvektoren,
   Konsistenzindex; hierarchische Strukturierung von Entscheidungsproblemen.
4. **TOPSIS:** Hwang & Yoon (1981) — Distanzbasiertes Rankingverfahren; Bewertung nach
   Nähe zur positiven Ideallösung und Distanz zur Anti-Ideallösung.
5. **Anwendungsbeispiele aus dem IT-Kontext:** Hanine et al. (2016) — AHP+TOPSIS für
   ETL-Software-Auswahl (strukturell analog zum KPI-Hub-Auswahlproblem);
   Zaidan et al. (2015) — AHP+TOPSIS für EMR-Software (domänenübergreifende Bestätigung).

> **[OFFENE ENTSCHEIDUNG KAP2-E2] Nutzwertanalyse in 2.4 — Quellengrundlage**
>
> - **Status:** Entschieden (Stand 24.04.2026, aktualisiert 28.04.2026: Key von `pohl2010` auf `pohlrupp2015` korrigiert — PDF ist englische Ausgabe Rocky Nook 2015)
> - **Option A (präferiert):** Nutzwertanalyse über Pohl & Rupp (2015) einführen — Abschnitt 8.3.2, S. 119 ff. Vorteil: keine
>   zusätzliche Quelle nötig; Zangemeister-Originalpublikation muss nicht beschafft werden.
> - **Option B:** Zangemeister (1971/1976) als Originalquelle beschaffen. Nachteil: sehr alte
>   Quelle, schwer zugänglich, unnötiger Aufwand wenn Pohl & Rupp ausreicht.
> - **Empfehlung:** Option A umgesetzt. `pohlrupp2015` als einzige Quelle für die Nutzwertanalyse
>   in 2.4 verwenden; Zangemeister nicht beschaffen.

### Quellen

| BibTeX-Key | Funktion |
|---|---|
| `pohlrupp2015` | Nutzwertanalyse und MoSCoW als RE-Priorisierungsmethoden |
| `velasquez2013` | MCDM-Methodenvergleich (Methodenbegründung) |
| `saaty1990` | AHP-Grundlagenwerk |
| `hwangyoon1981` | TOPSIS-Grundlagenwerk |
| `hanine2016` | AHP+TOPSIS angewendet auf IT-Software-Auswahl |
| `zaidan2015` | AHP+TOPSIS zweiter Anwendungsbeleg (Healthcare IT) |

### Übergang

Der Abschnitt schließt mit einer vorläufigen Methodeneignungsmatrix oder einem kurzen
Fazit: Für das vorliegende Entscheidungsproblem (ca. 5–7 Alternativen, mehrere gewichtete
Kriterien, IT-Kontext) erscheinen AHP und TOPSIS am geeignetsten — die endgültige Methodenwahl
und -begründung erfolgt in Kap. 7.1. Überleitung: "Bevor die herausgearbeiteten Methoden
angewendet werden können, sind die Defizite der bestehenden Ansätze zu systematisieren —
denn sie bestimmen, welche Kriterien im Bewertungsmodell überhaupt relevant sind."

### Seitenumfang

ca. 1,5–2,0 Seiten

---

## 2.5 Defizite bestehender Ansätze

**Argumentationsziel:** Der Leser soll nach diesem Abschnitt verstehen, warum bestehende
Lösungen das Problem der fragmentierten KPI-Landschaft nicht lösen — und warum deshalb ein
neues, integriertes Entscheidungsmodell notwendig ist. Dies ist der Syntheseabschnitt, der die
vier Grundlagenabschnitte (2.1–2.4) zusammenführt und die Forschungslücke explizit benennt.
Hänel fordert ausdrücklich: "Defizite fundiert herausarbeiten — Literatur, keine internen Docs."

### Gliederungspunkte

1. **BI-Fragmentierung als strukturelles Problem:** Larson & Chang (2016) + Baars & Kemper (2008)
   — empirischer Beleg, dass heterogene BI-Landschaften kein Einzelfall sind; Konsolidierung
   als "ungelöste Herausforderung".
2. **KPI-Definitionsheterogenität:** Giovannoni & Maraghini (2013) — Inkonsistente
   KPI-Definitionen als strukturelle Ursache (nicht nur technisches Problem); drei Quellen
   der Definitionsheterogenität.
3. **SSBI-Implementierungsdefizite:** Lennerholt et al. (2018) — datenbezogene, benutzerbezogene
   und organisationale Hindernisse bei SSBI; Passlick et al. (2020) — Akzeptanzparadox
   (stärkere Betonung von Datenqualität korreliert negativ mit Nutzungsabsicht).
4. **RBAC in heterogenen Systemen:** Ghazal et al. (2020) — domänenübergreifende
   Rollen-Harmonisierung als ungelöstes Problem; bestehende RBAC-Ansätze greifen in
   Multi-System-Kontexten nicht ohne zusätzliche Harmonisierungsschicht.
5. **Zwischenfazit — Forschungslücke:** Zusammenfassung: Die Literatur behandelt BI-Integration,
   RBAC und MCDM-Methoden getrennt. Ein integriertes Entscheidungsmodell, das alle drei
   Dimensionen für einen konkreten Enterprise-Kontext zusammenführt, existiert noch nicht.
   Damit ist die Forschungslücke begründet.

### Quellen

| BibTeX-Key | Funktion |
|---|---|
| `larson2016` | BI-Fragmentierung als strukturelles Unternehmensdesiderat |
| `baars2008` | Integrationsdefizit in BI-Architekturen |
| `giovannoni2013` | KPI-Definitionsheterogenität |
| `lennerholt2018` | SSBI-Implementierungsdefizite |
| `passlick2020` | SSBI-Akzeptanzparadox |
| `ghazal2020` | RBAC-Harmonisierung in heterogenen Systemen |

### Übergang zu Kapitel 3

"Die herausgearbeiteten Defizite zeigen: Das vorliegende Problem erfordert kein weiteres
theoretisches Review, sondern die Konstruktion eines neuen Artefakts — eines Entscheidungsmodells,
das die identifizierten Dimensionen integriert. Dies motiviert die Wahl von Design Science
Research als Forschungsmethodik, die im folgenden Kapitel begründet wird."

### Seitenumfang

ca. 1,0–1,5 Seiten

---

## Zusammenfassung: Seitenumfang Kapitel 2

| Abschnitt | Seitenumfang |
|---|---|
| 2.1 KPI-Management und Business Intelligence | 2,0–2,5 S. |
| 2.2 Enterprise-Systemintegration | ~2,5 S. (EA-Paradigma umgesetzt, **vollständig geschrieben**) |
| 2.3 Data Governance und Zugriffskontrolle | 1,5–2,0 S. |
| 2.4 Entscheidungsmethoden im Software Engineering | 1,5–2,0 S. |
| 2.5 Defizite bestehender Ansätze | 1,0–1,5 S. |
| **Gesamt** | **8,0–10,5 S. (Zielwert: 9 S.)** |

---

## Offene Entscheidungen (Zusammenfassung)

Alle Entscheidungen für Kap. 2 sind abgeschlossen. Kap. 2.1–2.5 vollständig geschrieben (Stand 28.04.2026).

| ID | Abschnitt | Entscheidung | Status | Empfehlung |
|---|---|---|---|---|
| KAP2-E1 | 2.2 | Embedding-Paradigma: eigener Abschnitt / Sonderfall / streichen | **Abgeschlossen** | Option A umgesetzt — `nijkamp2009` als akademische Primärquelle, EA als viertes eigenständiges Paradigma; Kap. 2.2 fertig geschrieben |
| KAP2-E2 | 2.4 | Nutzwertanalyse: Pohl (2010) ausreichend / Zangemeister beschaffen? | **Abgeschlossen** | Option A: `pohlrupp2015` reicht — kein Zangemeister nötig |

---

## Abhängigkeiten zu anderen Kapiteln

- **Kap. 5 (Anforderungsanalyse):** Baut auf den KPI-Definitionen (2.1), RBAC-Grundlagen (2.3)
  und Anforderungspriorisierungsmethoden (2.4 / Pohl 2010) auf.
- **Kap. 6 (Lösungsraum):** Integrationsparadigmen aus 2.2 bilden die konzeptuelle
  Strukturierungslogik für die Tool-Optionen.
- **Kap. 7 (Bewertungsmodell):** MCDM-Methoden aus 2.4 (AHP, TOPSIS) werden hier
  angewendet; 7.1 entscheidet endgültig die Methodenwahl.
- **Kap. 9 (Diskussion):** Defizite aus 2.5 sind der Maßstab, gegen den das Artefakt
  in der Diskussion gemessen wird.
