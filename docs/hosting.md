# Hosting

Zu hosten sind ein Docker-Container (Spring Boot mit Frontend) und eine PostgreSQL-Datenbank. Die Preise sind Stand November 2026 und können sich ändern.

## Vergleich

| Anbieter | Modell | Kosten pro Monat (ca.) | Datenbank | Aufwand | Bewertung |
| --- | --- | --- | --- | --- | --- |
| **Azure for Students** | PaaS (App Service + Azure Database for PostgreSQL) | 0 € für das Team: 100 $ Guthaben für 12 Monate, ohne Kreditkarte | Verwaltet | Mittel | Kostenlos für Studierende, verwaltete Datenbank, Erfahrung mit Azure DevOps im Team vorhanden |
| **Render** | PaaS | ca. 13 $ (Starter Web Service 7 $ + Postgres Basic 6 $) | Verwaltet | Gering | Sehr einfach (Deploy aus Git); 512 MB RAM im Starter-Plan sind für Spring Boot knapp |
| **Railway** | PaaS, nutzungsbasiert | ab 5 $ (Hobby, inkl. 5 $ Nutzung; darüber wird nach Verbrauch abgerechnet) | Verwaltet | Gering | Einfach, Kosten schwerer vorherzusagen |
| **Hetzner Cloud** | Eigener Server (VPS) | ca. 6 € (CX23) | Selbst betreiben (Docker Compose) | Hoch | Günstigster Server, aber Updates, Backups und Sicherheit liegen beim Team |

## Empfehlung

**Azure for Students.** Für die Projektdauer entstehen keine Kosten, die Datenbank wird verwaltet (Backups inklusive), und das Team kennt Azure bereits über Azure DevOps.

Falls das Guthaben aufgebraucht ist, ist **Render** die einfachste Alternative und **Hetzner** die günstigste.

## Quellen

- [Azure for Students: Angebot](https://azure.microsoft.com/en-us/offers/ms-azr-0170p/) und [FAQ](https://learn.microsoft.com/en-us/azure/education-hub/faq)
- [Render: Kosten für Web Service + Postgres](https://render.com/articles/how-much-does-cloud-application-hosting-cost-for-small-businesses)
- [Railway: Preispläne](https://docs.railway.com/pricing/plans)
- [Hetzner Cloud: Preise nach der Anpassung im Juni 2026 (Better Stack)](https://betterstack.com/community/guides/web-servers/hetzner-cloud-review/)
