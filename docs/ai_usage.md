# AI-Einsatz und Reflexion

## 1. AI-Einsatz

Wir haben Chat-basierte Large Language Models (u. a. Claude) an drei Stellen im Requirements Engineering eingesetzt:

1. **Funktionen sammeln** und auf MVP, V2 und V3 verteilen
2. **User Stories generieren** und priorisieren
3. **Anforderungen prüfen** auf Widersprüche, Lücken und Unklarheiten

Die Prompts sind gekürzt wiedergegeben.

## 2. Funktionen sammeln

**Prompt:**
> Wir entwickeln eine App, mit der WGs, Familien und Berufstätige ihre Haushaltsaufgaben gemeinsam organisieren. Sammle sinnvolle Funktionen und ordne sie einem MVP, einer V2 und einer V3 zu.

**Ergebnis:** eine Funktionsliste mit rund 170 Einträgen, verteilt auf MVP, V2 und V3.

**Kritische Bewertung:**
- **Hilfreich:** Die AI hat Randfälle aufgezeigt, die wir in den MVP übernommen haben, z. B. „Offene Aufgaben beim Austritt eines Mitglieds freigeben“, „Aufgaben ohne Fälligkeit berücksichtigen“ und „Bei Zeitablauf automatisch aktualisieren“.
- **Zu groß:** Der Gesamtumfang ist für ein Semester nicht umsetzbar. Wir haben den MVP auf einen vollständigen Anwendungsfall beschränkt; alles andere ist V2 bzw. V3.
- **Kein Bezug zum Problem:** z. B. Wetterbedingungen, Ruhezeiten, QR-Codes oder Materialbestände. Diese Funktionen stehen nur noch in V3.
- **Dubletten:** z. B. „Aufgabenserien“ zweimal in V2. In der README haben wir die Liste thematisch zusammengefasst.

## 3. User Stories generieren

**Prompt:**
> Erstelle aus unserer Projektidee 10 User Stories im Format „Als … möchte ich …, um …“ und priorisiere sie nach Must, Should und Could.

**Ergebnis:** 10 User Stories, davon 7 Must, 2 Should (V2) und 1 Could (V3). Die Must-Stories stehen als US-01 bis US-07 in `requirements.md`.

**Kritische Bewertung:**
- Format und Priorisierung sind grundsätzlich brauchbar.
- **Generisch:** Die Stories passen zu jeder To-do-App. Stories zu Haushalt, Einladen, Zuweisen und Übernehmen fehlen, obwohl diese Funktionen im MVP stehen.
- **Vage Nutzenangaben:** z. B. „um meinen Fortschritt zu verfolgen“ (US-07) oder „um Änderungen vorzunehmen“ (US-02).
- **Widerspruch:** Die Should-Story „Nach Deadline oder Priorität filtern“ ist V2, der MVP enthält aber bereits Filter und Sortierung nach Priorität. Deshalb haben wir sie nicht übernommen.
- **Neue Idee der AI:** Die Could-Story „KI-basierte Tagesplanung“ stammt nicht aus unserer Idee. Sie bleibt in V3 (automatische Planung).
- **Akzeptanzkriterien** wurden nicht erzeugt.

## 4. Anforderungen prüfen

**Prompt:**
> Prüfe unsere Anforderungen auf Widersprüche, Lücken und Unklarheiten. Achte besonders darauf, ob die Anforderungen testbar sind und ob der MVP im Semester realistisch ist.

**Ergebnis und kritische Bewertung:**

| Befund der AI | Bewertung | Konsequenz |
|---|---|---|
| „Zugriff auf Mitglieder des Haushalts beschränken“ steht in V3, NFA-04 verlangt Zugriffsschutz aber schon im MVP | Berechtigt | Korrigiert: In der README steht unter V3 nur noch die feingranulare Rechtevergabe |
| V2 berücksichtigt „persönliche Belastungsgrenzen“, festlegen kann man sie aber erst in V3 | Berechtigt | Korrigiert: In der README berücksichtigt V2 nur die Aufgabenlast |
| „Aufwand in Minuten“ und „Zeitaufwand (30/60/60+ min)“ wirken doppelt | Berechtigt | In `requirements.md` zu klären |
| FA-05: Die Priorisierungslogik ist nicht beschrieben, daher ist US-06 nicht testbar | Berechtigt | In `requirements.md` zu klären |
| Die FAs decken nur Aufgaben ab, nicht Konto, Haushalt und Zuständigkeit | Berechtigt | In `requirements.md` zu klären |
| Für den Stakeholder „Admin“ ist nicht festgelegt, was er im MVP darf | Berechtigt | In `requirements.md` zu klären |
| NFA-01 („intuitiv“) ist nicht messbar | Berechtigt | In `requirements.md` zu klären |
| Nur 7 User Stories, keine Akzeptanzkriterien | Berechtigt | In `requirements.md` zu ergänzen |
| Punkte werden im MVP berechnet, das Punktekonto kommt erst in V2 | Kein Widerspruch | Im MVP werden Punkte nur berechnet, die Gutschrift folgt in V2 |
| „Offene Aufgaben freigeben“ steht im MVP und in V2 | Kein Widerspruch | MVP = Austritt eines Mitglieds, V2 = Entfernen durch die Haushaltsverwaltung |

**Nicht übernommen:** Die AI hat zusätzlich eigene Lösungen vorgeschlagen und direkt in einen Entwurf von `mvp.md` geschrieben:
- eine Punkteformel für die Priorität
- Messkriterien für die NFAs (z. B. „2 von 3 Testpersonen“, Bildschirmbreiten 360–1920 px)
- Regeln für den Admin
- eine zusätzliche Must/Should-Aufteilung innerhalb des MVP

Diese Vorschläge haben wir verworfen. Sie waren teilweise übertrieben und standen nicht in unseren Anforderungen. Die AI hat sie trotzdem so formuliert, als wären sie bereits beschlossen.

## 5. Reflexion

- **Stärken:** AI liefert schnell Ideen und Struktur. Bei der Prüfung findet sie Widersprüche zwischen weit auseinanderliegenden Stellen, z. B. zwischen NFA-04 und der V3-Liste.
- **Schwächen:** AI vergrößert den Scope und bleibt generisch. Außerdem erfindet sie Details, die niemand beschlossen hat, und präsentiert sie als fertige Anforderungen.
- **Konsequenz:** Wir übernehmen AI-Ergebnisse nur nach Prüfung im Team und nur, wenn sie zu unserem Problem passen. Die Verantwortung für die Anforderungen liegt bei uns.
