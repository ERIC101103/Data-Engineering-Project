# Data Engineering Project · PMS Data Platform

Studienprojekt zur reproduzierbaren Bereitstellung eines Azure-Databricks-Lakehouse für das Projektmonitoring. Eine nächtliche Pipeline verarbeitet synthetische Projekt-, Kunden- und Komponentendaten und stellt sie für SQL-Abfragen und einen Agenten bereit.

**Stand am 24.11.2026** · Projektplanung. Die Basisarchitektur ist laut Projektbriefing mit der Lehrkraft abgestimmt. Die Umsetzung und Messungen stehen aus.

## Einstieg für die Lehrkraft

| Datei | Inhalt |
| --- | --- |
| [PLAN.md](PLAN.md) | Fahrplan, Abnahmekriterien und mein Lerntagebuch |
| [Architektur](docs/architektur.md) | Freigegebene Basis und der direkte Agent-Zugriff |
| [Entscheidungen](docs/entscheidungen.md) | Plattformwahl, Alternativen und offene Fragen |
| [Kostenmodell](docs/tco.md) | Azure-Guthaben, Messplan und Fünfjahres-TCO |
| [Übergabe](docs/uebergabe.md) | Demo, Betriebsanleitung und Rückbau |

Die Arbeitspakete stehen in den [GitHub Issues](https://github.com/ERIC101103/Data-Engineering-Project/issues). Die [Projekt-Roadmap](https://github.com/users/ERIC101103/projects/1/views/1) ist der vorgesehene Ort für die zeitliche Planung.

## Umsetzung

| Ordner | Geplanter Inhalt |
| --- | --- |
| [infra/terraform/](infra/terraform/README.md) | Terraform für Azure und Azure Databricks, einschließlich State-Bootstrap |
| [pipelines/](pipelines/README.md) | Geplanter Lakeflow Job und Transformationen in SQL oder PySpark |
| [data/](data/README.md) | Synthetische Testdaten und Datenverträge |
| [agents/](agents/README.md) | Agent-Werkzeug zur Abfrage der Gold-Tabelle |

Das Repository ist zur öffentlichen Einsicht vorgesehen. Beispiele und Demoausgaben verwenden synthetische Daten. Zugangsdaten, interne Systemdetails und Terraform-State bleiben in geschützten Umgebungen.
