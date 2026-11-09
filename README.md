# Aufgabenverwaltung mit automatischer Priorisierung

Projekt im Kurs **Principles of AI-based Software Engineering**, FH Technikum Wien.
**Gruppe 17:** Marko, Süleyman, Raul

## Projektüberblick

Eine Anwendung zur gemeinsamen Verwaltung von Haushaltsaufgaben. Mitglieder eines Haushalts legen Aufgaben an, schätzen Aufwand und Anstrengung ein und übernehmen Zuständigkeiten. Das System berechnet für jede Aufgabe automatisch eine Priorität und zeigt, welche Aufgabe als Nächstes erledigt werden sollte und warum.

Das Projekt ist in drei Ausbaustufen geplant: ein **MVP** mit der Kernfunktionalität, eine **V2** mit Aufgabenserien, Punktekonto und automatischer Zuweisung sowie eine **V3** mit erweiterter Priorisierung, automatischer Planung und Integrationen.

## Zielgruppe

- Studierende (z. B. Wohngemeinschaften)
- Berufstätige
- Familien

## Stakeholder

- **Nutzer:** Mitglieder eines Haushalts
- **Admin:** Haushaltsverwaltung

## Ausbaustufen

### MVP

- **Benutzerkonto:** registrieren, anmelden, abmelden, Passwort zurücksetzen
- **Haushalt:** erstellen, bearbeiten/umbenennen, löschen, Mitglieder einladen, verlassen; offene Aufgaben beim Austritt freigeben
- **Aufgaben:** erstellen, bearbeiten, löschen, Fälligkeit festlegen
- **Aufgabenbewertung und Punkte:** Aufwand in Minuten, Anstrengung auf fester Skala, Dringlichkeit und Wichtigkeit (Ja/Nein), Zeitaufwand (30 min, 60 min, 60+ min); daraus werden Aufgabenpunkte berechnet
- **Bearbeitungsstatus:** Status verfolgen, Erledigung bestätigen, erledigte Aufgaben wieder öffnen
- **Zuständigkeit:** Aufgaben manuell zuweisen oder freiwillig übernehmen
- **Aufgabenübersicht:** Haushalts- und persönliche Liste, Filter nach Status und Verantwortlichen, Sortierung nach Priorität
- **Automatische Priorisierung:** berücksichtigt manuelle Einschätzung, Fälligkeit, Überfälligkeit und Aufgaben ohne Fälligkeit; wird bei Änderungen und Zeitablauf neu berechnet und zeigt die Gründe für die berechnete Priorität

Details: [`docs/requirements.md`](docs/requirements.md)

### V2

- **Transparenz:** Berechnungsregel und verwendete Werte der Priorität anzeigen
- **Aufgabenserien:** wiederkehrende Aufgaben mit Periode, Start und Ende; einzelne Termine verschieben oder absagen; Änderungen auf einen, folgende oder alle Termine anwenden; Serien pausieren, bestimmte Wochentage
- **Erinnerungen und Benachrichtigungen:** vor Fälligkeit, bei Überfälligkeit, bei neuen Zuweisungen, tägliche Zusammenfassung, Anzeige in der App
- **Benutzerprofil:** Anzeigename, Profilbild, Sprache
- **Haushaltsverwaltung:** Rollen vergeben, Mitglieder entfernen, Einladungen widerrufen, Administration übertragen
- **Erweiterte Aufgabenfunktionen:** private Aufgaben, Archivieren, Wiederherstellen, frühester Bearbeitungsbeginn, Mehrfachbearbeitung, Duplizieren, Schutz vor gleichzeitigem Überschreiben, Pausieren und Fortsetzen
- **Aufgabenorganisation:** Räume, Kategorien, Checklisten, Vorlagen, Anleitungen
- **Zusammenarbeit:** Kommentare und Fotos an Aufgaben
- **Aufgabenübersicht:** Stichwortsuche, Kalenderansicht, Filter nach Raum und Kategorie
- **Verfügbarkeit und automatische Zuweisung:** verfügbare Zeiten und Abwesenheiten, Berücksichtigung von Aufgabenlast, Rotation bei wiederkehrenden Aufgaben, Zuweisungen ablehnen, begonnene Aufgaben vor Neuzuweisung schützen
- **Punktekonto und Punkteübersicht:** Gutschrift bei Erledigung, Rücknahme beim Wiederöffnen, Schutz vor Mehrfachgutschrift, konfigurierbare Berechnungsregel, Korrekturen mit Begründung, Punkte pro Mitglied und Zeitraum vergleichen

### V3

- **Berechtigungen:** festlegen, wer Aufgaben sehen, bearbeiten, löschen und zuweisen darf
- **Mehrere Haushalte** mit einem Konto, Aufgaben zwischen Haushalten kopieren
- **Aufgabenabhängigkeiten:** Voraussetzungen, Schutz vor Zirkeln, blockierte Aufgaben kennzeichnen und freigeben
- **Erweiterte Priorisierung:** Hygiene, Sicherheit, Abhängigkeiten, betroffene Mitglieder, Besuche, Aufschubfristen; konfigurierbare Gewichtung, Regeln je Kategorie, manuelles (zeitlich begrenztes) Überschreiben, Verlauf und Simulation von Regeländerungen
- **Fähigkeiten und Präferenzen** der Mitglieder bei der Zuweisung berücksichtigen
- **Gemeinsame Aufgabenverteilung:** Aufgabentausch, mehrere Verantwortliche, Punkte aufteilen
- **Automatische Planung (KI-gestützt):** nächste Aufgabe vorschlagen, Wochenpläne, saisonale Aufgaben, Bündelung nach Raum, Ruhezeiten, Wetter, Übernahme offener Aufgaben in den nächsten Tag
- **Qualitätskontrolle:** Abnahme von Aufgaben, Rückgabe zur Nachbearbeitung, Punkte erst nach Bestätigung
- **Zeiterfassung:** tatsächliche Bearbeitungszeit erfassen, Schätzungen daraus vorschlagen
- **Materialien und Einkaufsbedarf:** Bestände, Mindestmengen, Einkaufseinträge automatisch erzeugen
- **Protokoll und Auswertung:** Änderungsprotokoll, Aufwand und Punkteverteilung im Zeitverlauf
- **Integration und Zugriff:** Kalendersynchronisation, Offline-Bearbeitung, QR-Codes am Einsatzort, CSV-Export
- **Weitere Komfortfunktionen:** gespeicherte Filter, Mehrfachzuweisung, persönliche Belastungsgrenzen und Benachrichtigungszeiten

## Dokumentation

| Datei | Inhalt |
|---|---|
| [`docs/requirements.md`](docs/requirements.md) | Anforderungen und User Stories (MVP) |
| [`docs/mvp.md`](docs/mvp.md) | MVP-Scope, enthaltene und ausgeschlossene Funktionen |
| [`docs/ai-usage.md`](docs/ai-usage.md) | AI-Einsatz, Prompts, Ergebnisse und kritische Bewertung |

## Projektstatus

Phase 1: Definition und Anforderungen
