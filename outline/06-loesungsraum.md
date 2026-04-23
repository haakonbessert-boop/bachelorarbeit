# Kapitel 6 — Lösungsraum und Architektur-/Tooloptionen

**Hänel-Anforderung:** Welche Lösungsoptionen existieren? Analyse und Strukturierung des
Lösungsraums; nachvollziehbare Gegenüberstellung der Alternativen.

**Umfang-Zielwert:** 6 Seiten (laut THESIS_STATUS.md)

## Geplante Subsections (Stand 23.04.2026)

- 6.1 Überblick Lösungsraum
- 6.2 Option A — SAP Analytics Cloud (SAC)
- 6.3 Option B — SAP Build Work Zone
- 6.4 Option C — Weitere / Drittanbieter-Optionen
- 6.5 Vergleichsmatrix
- 6.6 Referenzprojekte *(NEU)*
- 6.7 Machbarkeitsbetrachtung *(NEU)*

---

## Offene Entscheidungen / Rückverweise

### [KAP6-E1] Gewichtungsmethodik für das Bewertungsmodell

- **Status:** Offen — Entscheidung fällt in Kap. 6 (spätestens Kap. 7)
- **Optionen:** AHP (Analytic Hierarchy Process) · Nutzwertanalyse · TOPSIS
- **Kontext:** Sachse hat alle drei Methoden als Ausgangspunkt benannt (Notiz 21.04.2026 in THESIS_STATUS.md).
  Kap. 2.5 "Entscheidungsmethoden" liefert die theoretische Einordnung.
- **Auswirkung auf andere Kapitel:**
  - `chapter/03Methodik.tex` ~Zeile 82: Formulierung "Gewichtungsmethodik offen: AHP, Nutzwertanalyse
    oder TOPSIS — wird in Kap. 6 entschieden" → nach Entscheidung durch konkrete Methode ersetzen
  - `outline/03-methodik.md` Offene Frage: "Welches Gewichtungsverfahren wird gewählt?" → abhaken
  - Kap. 7 Bewertungsmodell übernimmt die hier gewählte Methode direkt

### Checkliste für dieses Kapitel

- [ ] Gewichtungsmethodik entscheiden (AHP / Nutzwertanalyse / TOPSIS) und begründen
- [ ] Formulierung in `chapter/03Methodik.tex` ~Zeile 82 aktualisieren
- [ ] Offene Frage in `outline/03-methodik.md` Zeile 122 abhaken
