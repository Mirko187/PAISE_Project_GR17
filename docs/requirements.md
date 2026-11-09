# Anforderungen: Aufgabenverwaltung mit automatischer Priorisierung (MVP)

Dieses Dokument beschreibt daweil nur die Anforderungen an den **MVP**

## 1. Zielgruppe

- Studierende (z. B. Wohngemeinschaften)
- Berufstätige
- Familien

## 2. Stakeholder

| Stakeholder | Beschreibung |
|---|---|
| Nutzer | Mitglied eines Haushalts, das Aufgaben anlegt, übernimmt und erledigt |
| Admin | Haushaltsverwaltung |

## 3. User Stories

| ID | User Story | Priorität |
|---|---|---|
| US-01 | Als Nutzer möchte ich Aufgaben erstellen, um meine Tätigkeiten festzuhalten. | Must |
| US-02 | Als Nutzer möchte ich Aufgaben bearbeiten, um Änderungen vorzunehmen. | Must |
| US-03 | Als Nutzer möchte ich Aufgaben löschen, um meine Liste aktuell zu halten. | Must |
| US-04 | Als Nutzer möchte ich Deadlines festlegen, um Aufgaben rechtzeitig zu erledigen. | Must |
| US-05 | Als Nutzer möchte ich die Wichtigkeit einer Aufgabe angeben, damit sie bei der Priorisierung berücksichtigt wird. | Must |
| US-06 | Als Nutzer möchte ich eine automatisch priorisierte Aufgabenliste sehen, damit ich weiß, welche Aufgabe ich zuerst bearbeiten sollte. | Must |
| US-07 | Als Nutzer möchte ich Aufgaben als erledigt markieren, um meinen Fortschritt zu verfolgen. | Must |

## 4. Funktionsumfang

### 4.1 Benutzerkonto
- Registrieren
- Anmelden
- Abmelden
- Passwort zurücksetzen

### 4.2 Haushalt
- Erstellen
- Bearbeiten, einschließlich Umbenennen
- Löschen
- Mitglieder einladen
- Verlassen
- Offene Aufgaben beim Austritt eines Mitglieds freigeben

### 4.3 Aufgaben
- Erstellen
- Bearbeiten
- Löschen
- Fälligkeit festlegen

### 4.4 Aufgabenbewertung und Punkte
- Aufwand in Minuten schätzen
- Anstrengung auf einer festgelegten Skala bewerten
- Priorität automatisch einschätzen anhand von:
  - Dringlichkeit (Ja / Nein)
  - Wichtigkeit (Ja / Nein)
  - Zeitaufwand (30 min, 60 min oder 60+ min)
- Aufgabenpunkte anhand von Aufwand und Anstrengung berechnen

### 4.5 Bearbeitungsstatus
- Status verfolgen
- Erledigung bestätigen
- Erledigte Aufgaben wieder öffnen

### 4.6 Zuständigkeit
- Aufgaben manuell zuweisen
- Aufgaben freiwillig übernehmen

### 4.7 Aufgabenübersicht
- Alle Haushaltsaufgaben anzeigen
- Persönliche Aufgabenliste anzeigen
- Nach Status filtern
- Nach Verantwortlichen filtern
- Nach Priorität sortieren

### 4.8 Automatische Priorisierung
- Priorität berechnen
- Manuelle Prioritätseinschätzung berücksichtigen
- Fälligkeit berücksichtigen
- Überfälligkeit berücksichtigen
- Aufgaben ohne Fälligkeit berücksichtigen
- Nach Änderungen neu berechnen
- Bei Zeitablauf automatisch aktualisieren
- Gründe für die berechnete Priorität anzeigen

## 5. Funktionale Anforderungen

| ID | Anforderung |
|---|---|
| FA-01 | Das System muss das Erstellen, Bearbeiten und Löschen von Aufgaben ermöglichen. |
| FA-02 | Jede Aufgabe muss einen Titel und einen Status besitzen. |
| FA-03 | Nutzer müssen einer Aufgabe eine Deadline zuweisen können. |
| FA-04 | Nutzer müssen die Wichtigkeit einer Aufgabe festlegen können. |
| FA-05 | Das System muss Aufgaben anhand einer definierten Priorisierungslogik automatisch bewerten. |
| FA-06 | Die Aufgabenliste muss nach der berechneten Priorität sortiert werden können. |
| FA-07 | Nutzer müssen Aufgaben als erledigt markieren können. |

## 6. Nicht-funktionale Anforderungen

| ID | Anforderung |
|---|---|
| NFA-01 | Die Anwendung soll einfach und intuitiv bedienbar sein. |
| NFA-02 | Die Anwendung soll auf Desktop und Smartphones nutzbar sein. |
| NFA-03 | Aufgaben müssen mindestens 1 Jahr gespeichert werden. |
| NFA-04 | Die Anwendung muss Benutzerdaten vor unberechtigtem Zugriff schützen. |
| NFA-05 | 99 % aller Systemanfragen müssen in unter 100 ms bearbeitet werden. |

## 7. Offene Fragen

- Sortierung bei gleicher Priorität: zuerst nach Fälligkeit, danach nach Erstellungsdatum?
