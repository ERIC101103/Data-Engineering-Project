# Übergabe und Abschlusspräsentation

| Abschnitt | Was ich zeige |
| --- | --- |
| Problem und Ansatz | Eine Projektstatus-Frage, dazu Eingabedaten und erwartete Antwort |
| Plattformwahl | Kriterien, Alternativen und begründete Wahl von Azure Databricks |
| Deployment | Terraform-Struktur, Bootstrap, bereinigter Plan und reproduzierbarer Aufbau |
| Nachtlauf | Job-Historie, Abhängigkeiten, Gold-Ergebnis und Quarantäne |
| Agent | Dieselbe Projektfrage als API- und Agent-Aufruf, einschließlich eines Fehlerfalls |
| Kosten | Guthabenverbrauch, beobachtete Kosten und 5-Jahres-TCO für drei Szenarien |

## Betriebsanleitung zum Ausfüllen

- [ ] Voraussetzungen, Region, Rollen und eingesetzte Terraform- und Provider-Versionen dokumentieren.
- [ ] Einrichtungsreihenfolge vom State-Bootstrap bis zum Job und Agenten bestätigen.
- [ ] Start eines manuellen Laufs sowie Prüfung der geplanten Ausführung beschreiben.
- [ ] Wiederholung bei einem fehlgeschlagenen Teiljob und Prüfung der Quarantäne demonstrieren.
- [ ] Den Rückbau in umgekehrter Abhängigkeitsreihenfolge üben. Vor dem Löschen die Zielumgebung und den Destroy-Plan prüfen. State für abhängige Ressourcen bis zu deren Rückbau behalten.
- [ ] Abschließende Kostenkontrolle und öffentliche Demo-Artefakte mit Commit oder Tag verlinken.
