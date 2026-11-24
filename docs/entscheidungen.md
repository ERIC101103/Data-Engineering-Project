# Entscheidungslog

| ID | Entscheidung | Stand | Warum und was noch geprüft wird |
| --- | --- | --- | --- |
| E01 | Azure Databricks als Plattform der abgestimmten Architektur | Basis abgestimmt, Vergleich auszuarbeiten | Delta Lake, SQL und PySpark, Lakeflow Jobs, Unity Catalog und direkter SQL-API-Zugriff passen zum Zielbild. Terraform-Abdeckung, Schulsubscription und Kosten bleiben Prüfpunkte. |
| E02 | Agent direkt über die Databricks SQL API auf Gold | Vorgabe der Lehrkraft, technisch zu erproben | Ein festes SELECT-Werkzeug greift mit eigener Identität auf die Gold-Tabelle zu. Host, Authentifizierung und Fehlerbehandlung sind zu erproben. |
| E03 | Erst eine kleine Terraform-Übung, dann ein durchgängiger CSV-Batch | Umsetzungsvorschlag | Trennt Fehler bei Azure-Anmeldung und Terraform-State von Fehlern in der eigentlichen Datenpipeline. |
| E04 | Agent zunächst lesend betreiben | Umsetzungsvorschlag | Der Projektstatus bildet einen vollständigen, gut prüfbaren Anwendungsfall. Umfang und Genehmigungspfad für Schreibaktionen mit der Lehrkraft klären. |

## Plattformvergleich für die Präsentation

| Plattform | Weshalb sie in Betracht kommt | Was ich anhand des Kursprojekts prüfe |
| --- | --- | --- |
| Azure Databricks | Lakehouse mit Spark und SQL, Orchestrierung und direkter SQL-API | Kosten eines kleinen Jobs und Warehouses, Terraform-Abdeckung und verfügbare Rechte |
| Microsoft Fabric | Integrierte Azure-nahe Plattform mit OneLake und Power BI | Kapazität im Kurskonto, Terraform-Abdeckung für erforderliche Objekte und Agent-Zugriff |
| Snowflake | SQL-zentrierte Plattform mit getrenntem Compute und Storage | Vergleichbarer Batch-Pfad, Terraform- und API-Abdeckung, Abrechnung und Nutzbarkeit des Azure-Guthabens |

Für alle drei Optionen dieselben Mengen und Anforderungen verwenden. In der fertigen Entscheidung den Prüftag, die Quellen und den wichtigsten Nachteil der gewählten Plattform ergänzen.

## Vorlage für weitere Entscheidungen

- **Datum, Frage und Status**
- **Optionen und Entscheidungskriterien**
- **Entscheidung und Gründe**
- **Abstriche, offene Annahmen und Termin zur Überprüfung**
- **Quellen, Messwerte und zugehöriger Commit**
