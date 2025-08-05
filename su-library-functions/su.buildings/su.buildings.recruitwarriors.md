---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Buildings.RecruitWarriors

## SU.Buildings.RecruitWarriors(buildingID, settlerType, amount)

Gibt bei dem mit der ID angegebenen Gebäude auszubildende Soldaten in Auftrag.

#### Parameter

* `buildingID`: ID des Gebäudes
* `settlerType`: [settlers.md](../../api-enums/settlers.md "mention")
* `amount [0-100]`: Anzahl der auszubildenden Soldaten (100=unendlich)

#### Rückgabewert

* 1: erfolgreicher Aufruf (dies bedeutet nur, dass die Parameter valide waren und nicht zwingend, dass der Auftrag ausgeführt wird, z.B. wenn das Gebäude keine Kaserne ist!)
* 0: sonst / Fehler

#### Beispiel

```lua
local success = SU.Buildings.RecruitWarriors(buildingID, Settlers.BOWMAN_01, amount)
```
