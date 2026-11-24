# Testdaten

Für den ersten Batch synthetische Projekt-, Kunden- und Komponentendaten festlegen. Danach Checkpoint-Ereignisse mit Zeitstempel und Status ergänzen.

| Vorschlag | Schlüsselfelder |
| --- | --- |
| `projects.csv` | project_id, customer_id, project_name |
| `customers.csv` | customer_id, customer_name |
| `components.csv` | component_id, project_id, component_name |
| `checkpoints.csv` | checkpoint_id, project_id, event_time_utc, status |

Für Projekt P-1001 zwei gültige Checkpoints erstellen und das erwartete Ergebnis für den jüngsten Zeitpunkt dokumentieren. Dazu eine Dublette und einen Checkpoint mit ungültigem Datum einbauen. Vor der Implementierung Datentypen, Pflichtfelder, Zeitzone und fachliche Schlüssel festhalten.
