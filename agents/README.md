# Agent-Werkzeug für Projektstatus

Das geplante Werkzeug `get_project_status(project_id)` sendet eine feste parametrisierte SELECT-Abfrage an die Databricks SQL Statement Execution API. Die Demo liest eine Gold-Tabelle über ein SQL Warehouse und liefert den Projektstatus und letzten Checkpoint.

1. Identität und minimale Berechtigungen für die Tabelle und das Warehouse einrichten.
2. API mit einer bekannten Projekt-ID und begrenzter Ergebnismenge testen. Asynchrone Ergebnisse mit begrenzter Wartezeit abrufen.
3. Stabile Ausgaben für Treffer, unbekannte ID, Timeout und fehlende Berechtigung definieren.
4. Erst danach denselben Aufruf in eine Agent-Laufzeit einbinden und die Antwort mit dem SQL-Ergebnis vergleichen.

Agent-Host und Authentifizierungsmethode hängen vom verfügbaren Konto ab. Konkrete Wahl und Testnachweis im [Projektfahrplan](../PLAN.md) erfassen.
