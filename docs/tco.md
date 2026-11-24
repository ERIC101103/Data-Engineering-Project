# Azure-Guthaben und Fünfjahres-TCO

## Demo mit 100 € Azure-Guthaben

- Vor dem ersten kostenpflichtigen Lauf Währung, Guthaben, Subscription, Region und zugehörige Abrechnung prüfen.
- Falls im Kurskonto verfügbar, Budgetwarnungen bei 50 %, 75 % und 90 % setzen. Azure-Budgetwarnungen informieren über Ausgaben. Ressourcen laufen weiter, bis sie pausiert, beendet oder entfernt werden.
- Kurze Testläufe auf kleiner verfügbarer Compute-Größe durchführen. Warehouse-Auto-Stop, Job-Timeout und maximale Parallelität prüfen. Den Zeitplan erst für den Nachweis einschalten, danach pausieren.
- Pro Lauf Datum, Größe des Batches, Laufzeit, Compute-Einheiten und Storage erfassen. Ist-Kosten aus Azure Cost Management mit Verzögerung nachtragen. Guthaben und tatsächliche Verbrauchskosten getrennt ausweisen.

## Modell für 60 Monate

Die Eingabewerte sind Modellannahmen. Nach der Demo durch begründete Mengen und Messwerte ergänzen.

| Treiber | Klein | Mittel | Groß |
| --- | ---: | ---: | ---: |
| Eingangsvolumen pro Tag | 0,1 GB | 1 GB | 10 GB |
| Aufbewahrung | 90 Tage | 180 Tage | 365 Tage |
| Batchläufe pro Monat | 30 | 30 | 30 |
| Agent-Abfragen pro Monat | 100 | 1.000 | 10.000 |
| Job-Verbrauch je Lauf | offen | offen | offen |
| Warehouse-Laufzeit und Verbrauch pro Monat | offen | offen | offen |
| Speicher über Landing und Delta-Layer | offen | offen | offen |
| Kosten je Monat und auf 60 Monate | offen | offen | offen |

1. **Compute** = Job- und Warehouse-Verbrauch × jeweilige Einheitspreise. Separat abgerechnete VM-Kosten ergänzen. Bei Preisen mit enthaltenem Compute Doppelzählung vermeiden.
2. **Storage** = durchschnittlich belegte GB je Schicht × GB-Monatspreis, plus Transaktionen und ggf. Netzwerktransfer. Kompression, Datenkopien und Quarantäne berücksichtigen.
3. **Agent und Betrieb** = Modellaufrufe oder Tokens × Tarif, Monitoring und gegebenenfalls Betriebsstunden × Stundensatz.
4. **TCO** = einmalige Einrichtungskosten + Summe der 60 Monatskosten. Bei gleichbleibender Last entspricht die Summe 60 × Monatskosten. Für Wachstum jahresweise rechnen.

Zu jedem Preis Region, SKU, Einheit, Währung, Preisdatum und Quelle notieren. Für die Präsentation zusätzlich erläutern, wie sich längere Warehouse-Laufzeit oder höhere Datenaufbewahrung auswirken.

- [Azure Pricing Calculator](https://azure.microsoft.com/en-us/pricing/calculator/)
- [Azure Cost Management Budgets](https://learn.microsoft.com/en-us/azure/cost-management/tutorial-acm-create-budgets)
