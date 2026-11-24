# Projektfahrplan und Lerntagebuch

## Ausgangslage und Ziel

Ziel ist die Erstellung einer Azure Datenplattform mit Terraform (Infastructure as Code).

Die Kursvorgaben sind **100 € Azure-Guthaben**, ein nachvollziehbares Terraform-Deployment, ein nächtlicher Pipeline-Lauf, Bronze/Silver/Gold mit SQL-Anteil, Agent-Code, eine begründete Plattformwahl, eine Fünfjahres-TCO und eine Abschlusspräsentation mit Übergabe.

## Meilensteine

Die Reihenfolge ist ein erster Entwurf der Vorgehensweise.

| Phase | Was ich umsetze | Woran ich den Abschluss erkenne | Status |
| --- | --- | --- | --- |
| 0 · Problem und Plattform | Anwendungsfall, synthetische Eingaben und Datenumfang festlegen. Azure Databricks, Fabric und Snowflake anhand derselben Kriterien vergleichen. | Eingabe und erwartete SQL-Antwort dokumentiert. Plattformwahl mit zwei Alternativen begründet. | Offen |
| 1 · Erster Terraform-Durchlauf | Azure CLI und Terraform prüfen, Subscription, Region, Quoten und Rechte klären. In einer Übungs-Resource-Group `init`, `validate`, `plan`, `apply` und Rückbau üben. | Bereinigter Nachweis für den ersten Plan, einen zweiten Plan ohne Änderungen und den Rückbau liegt vor. | Offen |
| 2 · Lakehouse bereitstellen | Budgetwarnungen und Compute-Limits vorbereiten. State-Bootstrap, ADLS Gen2, Access Connector, Workspace und Unity-Catalog-Konfiguration umsetzen. | Terraform kann die Demo-Umgebung nachvollziehbar aufbauen. Databricks liest eine synthetische Datei aus ADLS. Voraussetzungen und Ausnahmen sind dokumentiert. | Offen |
| 3 · Datenpipeline | CSV → Landing → Bronze → Silver → Gold. Schritte einzeln testen und dann als nächtlichen Lakeflow Job mit festen Abhängigkeiten planen. | Historie zeigt einen geplanten Lauf. Gold liefert die erwartete Antwort. Wiederholung desselben Batches erzeugt keine doppelten Gold-Zeilen. Ein fehlerhafter Datensatz landet in Quarantäne. | Offen |
| 4 · Agent-Zugriff | Zuerst eine parametrisierte API-Abfrage mit einer Dienstidentität testen. Danach den gleichen Aufruf als Agent-Werkzeug anbinden. | Für P-1001 stimmen SQL-Ergebnis und Agent-Antwort überein. Unbekannte Projekt-ID und fehlende Rechte liefern nachvollziehbare Fehler. | Offen |
| 5 · Kosten und Übergabe | Laufzeiten und Verbrauch messen, TCO für drei Datenvolumina auf fünf Jahre rechnen, Demo und Wiederaufbau dokumentieren. | Kostenschätzung nennt Mengen, Annahmen, Preise und Quellen. Demo und Rückbau sind nach Anleitung nachvollziehbar. | Offen |

## Meine ersten drei Arbeitsschritte

1. Subscription und Guthaben prüfen. Region, Rolle, Provider-Freigaben und verfügbare SKUs festhalten.
2. Die kleinste Übungs-Resource-Group mit Terraform planen, prüfen, anwenden und wieder abbauen. In der Lernnotiz festhalten, was `plan`, `apply` und State jeweils tun.
3. Einen synthetischen Batch mit einer erwarteten Projektstatus-Abfrage definieren. Danach mit Storage und Databricks beginnen.

## Meine Fragen und Antworten

Die Fragen und Hypothesen sind vorbereitet. Eigene Beobachtungen und Antworten ergänze ich nach dem Versuch und verlinke den passenden Commit oder einen bereinigten Nachweis.

| ID | Meine Frage | Startannahme oder nächster Versuch | Meine Antwort / Nachweis |
| --- | --- | --- | --- |
| F01 | Welche Azure-Rechte habe ich für Workspace, Storage, Rollen und State? | Subscription und Rollen prüfen. Den ersten Plan in einer eigenen Resource Group ausführen. | Offen |
| F02 | Was ändert Terraform bei `plan`, was bei `apply`, und wofür brauche ich State? | Plan vor und nach dem ersten Apply vergleichen. Separaten Blob-Backend-Bootstrap ausprobieren. | Offen |
| F03 | Welche Ressourcen verwaltet der AzureRM-Provider und welche der Databricks-Provider? | Azure-Ressourcen und Workspace-Konfiguration getrennt planen. Unity-Catalog-Voraussetzungen prüfen. | Offen |
| F04 | Wie bleibt ein erneuter Nachtlauf desselben Batches ohne Dubletten? | Eindeutige Batch-ID und fachlichen Schlüssel festlegen. Gleichen Batch zweimal ausführen und Zeilenzahl prüfen. | Offen |
| F05 | Wie greift der Agent direkt auf Gold zu? | Dienstidentität, SQL Warehouse und parametrisierte Statement Execution API mit einer festen Projekt-ID testen. | Offen |
| F06 | Wie weit reicht das Guthaben und was treibt die Kosten im Betrieb? | Laufzeit, Compute-Verbrauch und Speichermengen für einen Beispieldurchlauf erfassen und hochrechnen. | Offen |

### Vorlage für einen Lern- oder Fehlereintrag

- **Datum, Phase und Frage**
- **Meine Vermutung vor dem Versuch**
- **Was ich ausprobiert habe**
- **Was passiert ist und woran ich hängen geblieben bin**
- **Meine Antwort und die Entscheidung, die ich daraus ableite**
- **Nächster Versuch / Commit / bereinigter Nachweis**

Architekturentscheidungen, die mehrere Phasen betreffen, halte ich zusätzlich im [Entscheidungslog](docs/entscheidungen.md) fest.
