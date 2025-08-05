---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Buildings.GarrisonWarriors

## SU.Buildings.GarrisonWarriors(buildingID)

Setzt das durch die ID angegebene Gebäude auf "zu besetzen".

#### Parameter

* `buildingID`: ID des zu besetzenden Gebäudes

#### Rückgabewert

* 1: erfolgreicher Aufruf (dies bedeutet nur, dass die Parameter valide waren und nicht zwingend, dass das Gebäude nun besetzt wird, z.B. wenn es kein Militärgebäude war!)
* 0: sonst / Fehler

#### Beispiel

```lua
local success = SU.Buildings.GarrisonWarriors(buildingID)
```
