---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Buildings.GetFirstBuilding

## SU.Buildings.GetFirstBuilding(playerID, buildingType, buildingState=Buildings.ALL)

Gibt die erste (=**älteste**) Gebäude-ID vom angegebenen Gebäude-Typs zurück um beispielsweise durch alle Gebäude dieses Typs zu iterieren. ⇒ [su.buildings.getnextbuilding.md](su.buildings.getnextbuilding.md "mention")

#### Parameter

* `playerID [1-8]`: Spieler-ID, **Index 0 ist ungültig!**
* `buildingType`: [buildings.md](../../api-enums/buildings.md "mention")
* `buildingState` (optional): Gebäude-Status nach dem gesucht werden soll, siehe [buildings.md](../../api-enums/buildings.md "mention")

#### Rückgabewert

* Gebäude-ID
* 0 falls keines vorhanden / Fehler

#### Beispiel

```lua
-- findet die erste (älteste) Baustelle eines kleinen Turms von Spieler 1
local buildingID = SU.Buildings.GetFirstBuilding(1, Buildings.GUARDTOWERSMALL, Buildings.UNDERCONSTRUCTION)
```
