# ADR-0001: Modularer Monolith statt Microservices

**Status:** Angenommen

## Kontext

Die Anwendung muss den MVP innerhalb eines Semesters mit drei Personen umsetzen. 99 % der Anfragen sollen unter 100 ms bleiben (NFA-05). Pro Haushalt gibt es nur wenige Nutzer und Aufgaben.

## Optionen

| Option | Vorteile | Nachteile |
| --- | --- | --- |
| Modularer Monolith (Spring Boot, eine Datenbank) | Ein Projekt, ein Deployment, schnelle Aufrufe im Prozess, wenig Infrastruktur | Module können nicht einzeln skaliert werden |
| Microservices (ein Service pro Bereich, Gateway, Message Queue) | Unabhängige Skalierung und Deployments | Viel Infrastruktur, verteilte Fehler, Netzwerk-Latenz, hoher Aufwand für drei Personen |

## Entscheidung

Wir bauen einen **modularen Monolithen** mit vier Modulen: Konto, Haushalt, Aufgaben, Priorisierung. Module greifen nur über ihre öffentlichen Schnittstellen aufeinander zu, nicht direkt auf fremde Tabellen.

## Konsequenzen

- Einfache Entwicklung, Tests und Hosting (ein Container + PostgreSQL).
- Die klare Modultrennung erlaubt es, später einzelne Module auszulagern, falls das nötig wird.
- Skalierung erfolgt nur als Ganzes, was für die erwartete Last ausreicht.
