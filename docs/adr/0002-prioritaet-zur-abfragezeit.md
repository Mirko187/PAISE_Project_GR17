# ADR-0002: Priorität bei der Abfrage berechnen statt speichern

**Status:** Angenommen

## Kontext

Die Priorität hängt von Wichtigkeit, Dringlichkeit, Fälligkeit und Überfälligkeit ab. Sie muss nach jeder Änderung und **bei Zeitablauf automatisch aktualisiert** werden (z. B. wenn eine Aufgabe überfällig wird). Zusätzlich sollen die Gründe für die Priorität angezeigt werden.

## Optionen

| Option | Vorteile | Nachteile |
| --- | --- | --- |
| Priorität speichern, per zeitgesteuertem Job neu berechnen | Sortierung direkt in der Datenbank | Werte veralten zwischen zwei Läufen; zusätzlicher Job; Gründe müssen ebenfalls gespeichert werden |
| Priorität bei jeder Abfrage berechnen | Immer aktuell, auch bei Zeitablauf; kein Job; Gründe entstehen bei der Berechnung | Rechenaufwand bei jeder Abfrage |

## Entscheidung

Das Priorisierungs-Modul **berechnet Priorität und Gründe bei jeder Abfrage** aus den gespeicherten Aufgabendaten und dem aktuellen Datum. Es wird nichts davon gespeichert. Bei gleicher Priorität wird nach Fälligkeit und danach nach Erstellungsdatum sortiert.

## Konsequenzen

- "Nach Änderungen neu berechnen" und "bei Zeitablauf aktualisieren" sind automatisch erfüllt.
- Ein Haushalt hat nur wenige Dutzend bis Hunderte offene Aufgaben; die Berechnung im Speicher bleibt deutlich unter dem 100-ms-Ziel.
- Sollte die Aufgabenanzahl stark wachsen, kann später ein Cache ergänzt werden.
