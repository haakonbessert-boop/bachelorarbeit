# Agent-Team — Dispatcher-Anleitung

## Verfügbare Agents

| Agent | Datei | Kernaufgabe |
|-------|-------|-------------|
| **Projektmanager** | `projektmanager.md` | Zeitmanagement, Fortschrittskontrolle, THESIS_STATUS |
| **Planer** | `planer.md` | Kapitelstruktur, Argumentation, Lückenanalyse |
| **Autor** | `autor.md` | LaTeX-Texte schreiben/überarbeiten |
| **Rechercheur** | `rechercheur.md` | Literaturverwaltung, Zitations-Check, Seitenzahlen |
| **Qualitätsprüfer** | `qualitaet.md` | Konventionen, Glossar, Sprache, Build |
| **Compliance** | `compliance.md` | Formalia, KI-Protokoll, Git-Workflow, SAP-Regeln |
| **SAP-Praxis** | `sap-praxis.md` | Stakeholder, Meetings, Zugänge, Praxisphase |
| **Redakteur** | `redakteur.md` | Repo-Hygiene, Verdichtung, Redundanzen, Konsistenz |
| **Lektor** | `lektor.md` | Korrekturlesen, Stil, Argumentation, Lesbarkeit |

## Aufruf-Beispiele

### Einzelner Agent
> "Lass den Qualitätsprüfer über Kapitel 3 laufen"

### Mehrere parallel
> "Lass Rechercheur, Qualitätsprüfer und Compliance parallel laufen"

### Kombination mit Aufgabe
> "Lass den Autor Kapitel 2.1 schreiben, Thema: Enterprise BI-Integration"

### Feierabend-Routine
> "Feierabend" → startet Projektmanager mit Feierabend-Aufgabe

### SAP-Praxis
> "Bereite das Janine-Meeting vor" → SAP-Praxis Agent
> "Welche Zugänge fehlen noch?" → SAP-Praxis Agent

### Korrekturlesen
> "Lies mal Kapitel 3 Korrektur" → Lektor
> "Ist der Text in 3.1 gut?" → Lektor

### Repo aufräumen
> "Das Repo wird unübersichtlich" → Redakteur
> "Prüf mal ob die Notes noch aktuell sind" → Redakteur

## Wie es funktioniert

1. Du gibst mir den Auftrag
2. Ich lese die passende(n) Agent-Datei(en)
3. Ich starte die Agents parallel (wenn unabhängig) oder sequenziell
4. Jeder Agent arbeitet auf den Projektdateien und gibt einen strukturierten Bericht zurück
5. Ich fasse die Ergebnisse für dich zusammen

## Einschränkungen

- Agents haben keinen eigenen Chatverlauf — jeder Aufruf ist ein frischer Start
- Agents können keine anderen Agents starten (kein Kaskadieren)
- Schreibzugriffe auf dieselbe Datei dürfen nicht parallel laufen (Konflikte)
- Der Autor-Agent sollte nie parallel mit dem Qualitätsprüfer auf demselben Kapitel arbeiten
