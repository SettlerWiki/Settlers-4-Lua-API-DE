---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Buildings.CrushBuildingsInArea

## SU.Buildings.CrushBuildingsInArea(playerID, buildingType, x, y, radius, buildingState=Buildings.ALL, killInhabitantsAndWorker=0)

Reißt Gebäude/Baustellen im angegebenen Bereich ab und gibt 50% der bisher verwendeten Rohstoffe (abgerundet) zurück. Insassen (Soldaten) und Arbeiter überleben je nach Einstellung.

Dies kann unter anderem genutzt werden, um den Spieler am Bau bestimmter Gebäude zu hindern.

#### Parameter

* `playerID`: ID des Spielers (1-8), Index 0 ungültig, -1 wenn keine Spieler gefiltert werden sollen
* `buildingType`: [buildings.md](../../api-enums/buildings.md "mention")
* `x, y`: Koordinaten
* `radius [0-74]`: Radius
* `buildingState` (optional): Gebäudestatus der abgerissen werden soll ( [buildings.md](../../api-enums/buildings.md "mention") )
* `killInhabitantsAndWorker` (optional): bei 1 werden Insassen (Soldaten) und Arbeiter des Gebäudes (auch wenn sie gerade außerhalb sind) getötet

#### Rückgabewert

none

#### Beispiel

```lua
-- reißt vom Spieler 1 alle Baustellen an 320,170 im Radius von 15 ab
SU.Buildings.CrushBuildingsInArea(1, -1, 320, 170, 15, Buildings.UNDERCONSTRUCTION)
```
