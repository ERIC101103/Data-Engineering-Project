# Terraform

Geplante Reihenfolge der Terraform-Konfigurationen.

| Geplanter Bereich | Inhalt |
| --- | --- |
| `bootstrap/` | Resource Group, Storage und Container für den getrennten Terraform-State |
| `azure/` | Projekt-Resource-Group, ADLS Gen2, Databricks Access Connector, Berechtigungen, Workspace und Budgetwarnungen, soweit im Kurskonto verfügbar |
| `databricks/` | Unity Catalog und Workspace-Objekte wie Job, Warehouse und Grants, soweit administrativ verfügbar |

Erste Übung in einer eigenen Resource Group. Nach Azure-Anmeldung die aktive Subscription prüfen. Sobald die Terraform-Dateien vorhanden sind, den Ablauf `terraform init` → `terraform fmt -check` → `terraform validate` → `terraform plan` → Prüfung → `terraform apply` üben. Danach einen erneuten Plan prüfen und die Übungsressourcen kontrolliert abbauen.

Den State-Container zuerst mit einer separat dokumentierten Konfiguration bereitstellen. Für den eigentlichen Plattform-State Azure Blob Storage mit Entra-Authentifizierung und State-Locking einrichten. Verwendete Terraform- und Provider-Versionen festhalten und den Provider-Lockfile versionieren.

- [Terraform AzureRM-Backend](https://developer.hashicorp.com/terraform/language/backend/azurerm)
