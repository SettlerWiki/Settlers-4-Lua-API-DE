---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Buildings.GetPreviousBuilding

## SU.Buildings.GetPreviousBuilding(buildingID, buildingState=Buildings.ALL)

Gibt die vorherige (=**neuere**) Gebäude-ID zurück.

Dies ist eine auf Gebäude reduzierte Version von [su.entity.getpreviousentityid.md](../su.entity/su.entity.getpreviousentityid.md "mention").

#### Parameter

* `buildingID`: ID des aktuellen Gebäudes
* `buildingState` (optional): Gebäude-Status nach dem gesucht werden soll, siehe [buildings.md](../../api-enums/buildings.md "mention")

#### Rückgabewert

* Gebäude-ID
* 0 falls keines vorhanden / Fehler

#### Beispiel

```lua
-- findet das vorherige (neuere) Gebäude ausgehen vom Gebäude mit ID 135
local previousBuildingID = SU.Buildings.GetPreviousBuilding(135)
```
