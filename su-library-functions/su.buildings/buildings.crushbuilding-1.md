---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Buildings.DeleteBuildingsInArea

## SU.Buildings.DeleteBuildingsInArea(playerID, buildingType, x, y, radius, buildingState=Buildings.ALL, buildingDestroyMode=2, killInhabitantsAndWorker=0)

Reißt Gebäude/Baustellen im angegebenen Bereich ab und gibt keine Rohstoffe zurück (je nach Einstellung). Insassen (Soldaten) und Arbeiter überleben je nach Einstellung.

Dies kann unter anderem genutzt werden, um den Spieler am Bau bestimmter Gebäude zu hindern.

#### Parameter

* `playerID [1-8]`: Spieler-ID, **Index 0 ist ungültig!**
* `buildingType`: [buildings.md](../../api-enums/buildings.md "mention")
* `x, y`: Koordinaten
* `radius [0-74]`: Radius
* `buildingState` (optional): Gebäudestatus der abgerissen werden soll ( [buildings.md](../../api-enums/buildings.md "mention") )
* `buildingDestroyMode` (optional): 0 nichts passiert, 1 wie [buildings.crushbuilding.md](buildings.crushbuilding.md "mention") (gibt Rohstoffe zurück), 2 wie [buildings.delete.md](../../library-functions/buildings/buildings.delete.md "mention") (keine Rohstoffe)
* `killInhabitantsAndWorker` (optional): bei 1 werden Insassen (Soldaten) und Arbeiter des Gebäudes (auch wenn sie gerade außerhalb sind) getötet

#### Rückgabewert

none

#### Beispiel

```lua
-- reißt vom Spieler 1 alle Baustellen an 320,170 im Radius von 15 ab und gibt keine Rohstoffe zurück
SU.Buildings.DeleteBuildingsInArea(1, -1, 320, 170, 15, Buildings.UNDERCONSTRUCTION)
```
