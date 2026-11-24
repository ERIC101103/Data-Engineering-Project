# Nächtliche Datenpipeline

Der erste Lakeflow Job läuft manuell. Nach den Prüfungen einen Nachtzeitplan mit expliziter Zeitzone dokumentieren und einen echten geplanten Lauf nachweisen.

| Jobschritt | Eingabe und Ausgabe | Prüfkriterium |
| --- | --- | --- |
| Landing | Synthetischer CSV-Batch → unveränderte Dateien mit Batch-ID in ADLS | Datei und Batch-ID sind nachvollziehbar |
| Bronze | Landing → Delta mit Herkunft, Ladezeit und Batch-ID | Zeilenzahl entspricht der Quelle |
| Silver | Bronze → typisierte, deduplizierte Daten und Quarantäne | Fehlerfall ist sichtbar, gültige Schlüssel sind eindeutig |
| Gold | Silver → Projektstatus und später Faktentabelle und Dimensionen | Erwartete SQL-Abfrage liefert definiertes Ergebnis |

Job-Schritte sequenziell verknüpfen. Wiederholungen mit derselben Batch-ID testen. SQL für Datenmodell, Transformation oder Abnahmeabfrage einplanen. Für die Demo genügen eine bekannte Projekt-ID, ein fehlerhafter Datensatz und eine wiederholte Batch-Verarbeitung.
