---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Buildings.GetNextBuilding

## SU.Buildings.GetNextBuilding(buildingID, buildingState=Buildings.ALL)

Gibt die nächste (=**ältere**) Gebäude-ID zurück.

Dies ist eine auf Gebäude reduzierte Version von [su.entity.getnextentityid.md](../su.entity/su.entity.getnextentityid.md "mention").

#### Parameter

* `buildingID`: ID des aktuellen Gebäudes
* `buildingState` (optional): Gebäude-Status nach dem gesucht werden soll, siehe [buildings.md](../../api-enums/buildings.md "mention")

#### Rückgabewert

* Gebäude-ID
* 0 falls keines vorhanden / Fehler

#### Beispiel

```lua
-- findet das nächste (ältere) Gebäude ausgehen vom Gebäude mit ID 135
local nextBuildingID = SU.Buildings.GetNextBuilding(135)
```
