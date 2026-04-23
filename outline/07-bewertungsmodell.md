# Kapitel 7 — Entscheidungs- und Bewertungsmodell

**Hänel-Anforderung:** Wie wird die Entscheidung zwischen den Lösungsoptionen strukturiert und
begründet? Scoring-Modell aufbauen und anwenden; Entscheidung nachvollziehbar dokumentieren.

**Umfang-Zielwert:** 8 Seiten (laut THESIS_STATUS.md)

## Geplante Subsections (Stand 23.04.2026)

- 7.1 Wahl der Bewertungsmethodik *(NEU — Entscheidung aus Kap. 6 übernehmen)*
- 7.2 Kriterienkatalog (aus Kap. 5 abgeleitet)
- 7.3 Gewichtung der Kriterien
- 7.4 Bewertung der Alternativen
- 7.5 Ergebnis und Handlungsempfehlung

---

## Offene Entscheidungen / Rückverweise

### [KAP7-E1] MVP-Zielsystem: Build Work Zone vs. SAP Analytics Cloud

- **Status:** Offen — Entscheidung fällt in Kap. 7 (spätestens Kap. 8)
- **Optionen:**
  - SAP Build Work Zone (wahrscheinlichste Option laut Kap. 3.3)
  - SAP Analytics Cloud (SAC) als Alternative
  - Weiteres Einbettungssystem (falls weder BWZ noch SAC geeignet)
- **Kontext:** Quellsysteme sind bereits belegt (Jira + ServiceNow); nur das Zielsystem ist offen.
  Das Bewertungsmodell aus diesem Kapitel liefert die Entscheidungsgrundlage.
- **Auswirkung auf andere Kapitel nach Entscheidung:**
  - `chapter/03Methodik.tex` ~Zeile 108: Offene Formulierung zum Zielsystem (aktuell:
    "Build Work Zone als wahrscheinlichste Option, SAP Analytics Cloud als Alternative;
    wird in Kap. 7/8 festgelegt") → durch gewähltes Zielsystem ersetzen
  - `outline/03-methodik.md` Offene Frage: "Zielsystem MVP: Build Work Zone oder SAP
    Analytics Cloud?" → abhaken
  - Kap. 8 MVP-Umsetzung baut direkt auf dieser Entscheidung auf

### [KAP7-E2] Gewichtungsmethodik (Abhängigkeit von Kap. 6)

- **Status:** Abhängig von [KAP6-E1] — Methode wird in Kap. 6 gewählt, hier angewendet
- Subsection 7.1 dokumentiert die Methodenwahl und begründet sie im Kontext des
  konkreten Entscheidungsproblems

### Checkliste für dieses Kapitel

- [ ] MVP-Zielsystem entscheiden (Build Work Zone / SAC / Alternative) und begründen
- [ ] Formulierung in `chapter/03Methodik.tex` ~Zeile 108 aktualisieren
- [ ] Offene Frage in `outline/03-methodik.md` Zeile 123 abhaken
- [ ] Gewichtungsmethodik aus Kap. 6 in Abschnitt 7.1 aufnehmen und anwenden
