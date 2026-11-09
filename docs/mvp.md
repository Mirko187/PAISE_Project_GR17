# MVP-Scope – Aufgabenverwaltung mit automatischer Priorisierung

## 1. MVP-Scope

Der MVP umfasst die Kernfunktionalität: Mitglieder eines Haushalts legen Aufgaben an, bewerten sie und übernehmen Zuständigkeiten. Das System berechnet für jede Aufgabe automatisch eine Priorität und zeigt, welche Aufgabe als Nächstes erledigt werden sollte und warum.

**Demonstrierbarer Anwendungsfall:**

1. Ein Nutzer registriert sich, erstellt einen Haushalt und lädt Mitglieder ein.
2. Er legt eine Aufgabe mit Fälligkeit, Aufwand, Anstrengung, Dringlichkeit, Wichtigkeit und Zeitaufwand an.
3. Das System berechnet Priorität und Aufgabenpunkte, sortiert die Aufgabenübersicht und zeigt die Gründe für die Priorität an.
4. Ein Mitglied übernimmt die Aufgabe und bestätigt die Erledigung.

**User Stories:**

- Der MVP deckt die Must-Stories US-01 bis US-07 ab (siehe `requirements.md`).
- Die Should-Story „Erinnerungen erhalten“ gehört zu V2.
- Die Could-Story „KI-basierte Empfehlungen zur Tagesplanung“ gehört zu V3.

## 2. Enthaltene Funktionen

- **Benutzerkonto**
  - Registrieren
  - Anmelden
  - Abmelden
  - Passwort zurücksetzen
- **Haushalt**
  - Erstellen
  - Bearbeiten, einschließlich Umbenennen
  - Löschen
  - Mitglieder einladen
  - Verlassen
  - Offene Aufgaben beim Austritt eines Mitglieds freigeben
- **Aufgaben**
  - Erstellen
  - Bearbeiten
  - Löschen
  - Fälligkeit festlegen
- **Aufgabenbewertung und Punkte**
  - Aufwand in Minuten schätzen
  - Anstrengung auf einer festgelegten Skala bewerten
  - Priorität automatisch einschätzen anhand von Dringlichkeit (Ja/Nein), Wichtigkeit (Ja/Nein) und Zeitaufwand (30 min, 60 min oder 60+ min)
  - Aufgabenpunkte anhand von Aufwand und Anstrengung berechnen
- **Bearbeitungsstatus**
  - Status verfolgen
  - Erledigung bestätigen
  - Erledigte Aufgaben wieder öffnen
- **Zuständigkeit**
  - Aufgaben manuell zuweisen
  - Aufgaben freiwillig übernehmen
- **Aufgabenübersicht**
  - Alle Haushaltsaufgaben anzeigen
  - Persönliche Aufgabenliste anzeigen
  - Nach Status filtern
  - Nach Verantwortlichen filtern
  - Nach Priorität sortieren
- **Automatische Priorisierung**
  - Priorität berechnen
  - Manuelle Prioritätseinschätzung berücksichtigen
  - Fälligkeit berücksichtigen
  - Überfälligkeit berücksichtigen
  - Aufgaben ohne Fälligkeit berücksichtigen
  - Nach Änderungen neu berechnen
  - Bei Zeitablauf automatisch aktualisieren
  - Gründe für die berechnete Priorität anzeigen

**Offene Frage:** Bei gleicher Priorität zuerst nach Fälligkeit und anschließend nach Erstellungsdatum sortieren? (siehe `requirements.md`, Abschnitt 7)

## 3. Ausgeschlossene Funktionen

Die folgenden Funktionen sind nicht Teil des MVP, weil sie für den Anwendungsfall nicht notwendig sind. Viele bauen außerdem auf dem MVP auf, z. B. das Punktekonto auf der Punkteberechnung oder die automatische Zuweisung auf der Zuständigkeit.

### V2

- **Transparenz:** Berechnungsregel und verwendete Werte der Priorität anzeigen
- **Aufgabenserien:**
  - Periode, Start und Ende festlegen
  - einzelne Termine verschieben oder absagen
  - Status, Zuständigkeit und Erledigung pro Termin speichern
  - Änderungen auf einen, die folgenden oder alle Termine anwenden
  - Umgang mit offenen Terminen festlegen
  - Serien pausieren, bestimmte Wochentage festlegen
- **Erinnerungen und Benachrichtigungen:**
  - vor Fälligkeit, bei Überfälligkeit, bei neuen Zuweisungen
  - tägliche Zusammenfassung
  - Anzeige in der App
- **Benutzerprofil:** Anzeigename, Profilbild, Sprache
- **Haushaltsverwaltung:**
  - Rollen vergeben
  - Mitglieder entfernen und deren offene Aufgaben freigeben
  - Einladungen widerrufen
  - Administration übertragen
- **Erweiterte Aufgabenfunktionen:**
  - private Aufgaben, Archivieren, Wiederherstellen
  - frühester Bearbeitungsbeginn
  - Mehrfachbearbeitung, Duplizieren
  - Schutz vor gleichzeitigem Überschreiben
  - Pausieren und Fortsetzen
- **Aufgabenorganisation:** Räume, Kategorien, Checklisten, Vorlagen, Anleitungen
- **Zusammenarbeit:** Kommentare und Fotos an Aufgaben
- **Aufgabenübersicht:** Stichwortsuche, Kalenderansicht, Filter nach Raum und Kategorie
- **Verfügbarkeit und automatische Zuweisung:**
  - verfügbare Zeiten und Abwesenheiten
  - Aufgabenlast berücksichtigen
  - Rotation bei wiederkehrenden Aufgaben
  - Zuweisungen ablehnen
  - begonnene Aufgaben vor Neuzuweisung schützen
- **Punktekonto und Punkteübersicht:**
  - Gutschrift bei Erledigung, Rücknahme beim Wiederöffnen
  - Schutz vor Mehrfachgutschrift
  - eigenen Punktestand anzeigen
  - Punkte bei späterem Löschen erhalten
  - konfigurierbare Berechnungsregel, Korrekturen mit Begründung
  - Punkte pro Mitglied und Zeitraum vergleichen

### V3

- **Berechtigungen:** festlegen, wer Aufgaben sehen, bearbeiten, löschen und zuweisen darf
- **Mehrere Haushalte** mit einem Konto, Aufgaben zwischen Haushalten kopieren
- **Aufgabenabhängigkeiten:**
  - Voraussetzungen festlegen
  - Schutz vor Zirkeln
  - blockierte Aufgaben kennzeichnen und freigeben
- **Erweiterte Priorisierung:**
  - Hygiene, Sicherheit, Abhängigkeiten, betroffene Mitglieder, Besuche, Aufschubfristen
  - konfigurierbare Gewichtung, Regeln je Kategorie
  - manuelles (zeitlich begrenztes) Überschreiben
  - Verlauf und Simulation von Regeländerungen
- **Fähigkeiten und Präferenzen** der Mitglieder bei der Zuweisung berücksichtigen
- **Gemeinsame Aufgabenverteilung:** Aufgabentausch, mehrere Verantwortliche, Punkte aufteilen
- **Automatische Planung (KI-gestützt):**
  - nächste Aufgabe vorschlagen, Wochenpläne
  - saisonale Aufgaben, Bündelung nach Raum
  - Ruhezeiten, Wetter
  - Übernahme offener Aufgaben in den nächsten Tag
- **Qualitätskontrolle:** Abnahme von Aufgaben, Rückgabe zur Nachbearbeitung, Punkte erst nach Bestätigung
- **Zeiterfassung:** tatsächliche Bearbeitungszeit erfassen, Schätzungen daraus vorschlagen
- **Materialien und Einkaufsbedarf:** Bestände, Mindestmengen, Einkaufseinträge automatisch erzeugen
- **Protokoll und Auswertung:** Änderungsprotokoll, Aufwand und Punkteverteilung im Zeitverlauf
- **Integration und Zugriff:** Kalendersynchronisation, Offline-Bearbeitung, QR-Codes am Einsatzort, CSV-Export
- **Weitere Komfortfunktionen:**
  - gespeicherte Filter, Mehrfachzuweisung
  - persönliche Belastungsgrenzen und Benachrichtigungszeiten
  - Punkteänderungen nur auf nicht begonnene Aufgaben anwenden

## 4. Abhängigkeiten und Kosten

- **MVP:** Es werden keine kostenpflichtigen externen APIs benötigt. Einzige externe Abhängigkeit ist ein E-Mail-Dienst für „Passwort zurücksetzen“.
- **V2 und V3:** Erst hier kommen externe Dienste hinzu, z. B. Benachrichtigungen, Kalendersynchronisation, Wetterdaten und eine AI-API für die KI-gestützte Planung. Deren Kosten werden vor der jeweiligen Ausbaustufe geprüft.
