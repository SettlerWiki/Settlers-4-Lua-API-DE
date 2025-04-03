---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Settlers.AddSettlersWithBeds

## SU.Settlers.AddSettlersWithBeds(x, y, playerID, settlerType, amount)

Erzeugt Siedler an den angegebenen Koordinaten und fügt dem Spieler zusätzlich entsprechende Betten hinzu, damit diese neuen Siedler nicht zu Streikenden führen können.

#### Parameter

* `x, y`: Koordinaten
* `playerID [1-8]`: Spieler-ID, **Index 0 ist ungültig!**
* `settlerType`: [settlers.md](../../api-enums/settlers.md "mention")
* `amount`: Anzahl der hinzuzufügenden Siedler (inkl. Betten)

#### Beispiel

```lua
SU.Settlers.AddSettlersWithBeds(403, 378, 1, Settlers.SQUADLEADER, 1) --//Ein Hauptmann für Spieler 1 bei den Koordinaten 403/378
SU.Settlers.AddSettlersWithBeds(100, 300, 1, Settlers.SLAVED_SETTLER, 25)  --//25 versklavte Siedler (können nicht im Editor platziert werden) für Spieler 1 bei den Koordinaten 100/300
```
