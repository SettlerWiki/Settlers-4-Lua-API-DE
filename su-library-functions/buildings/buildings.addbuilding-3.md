---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Buildings.AddConstructionSiteEx

## SU.Buildings.AddConstructionSiteEx(x, y, playerID, buildingType\[, radius=24])

Platziert eine Baustelle des angegebenen Gebäude-Typs für den genannten Spieler möglichst nahe an den angegebenen Koordinaten. Dabei wird im gegebenen Radius nach einer freien Stelle gesucht, an der die Baustelle platziert werden kann.

#### Parameter

* `x, y`: Koordinaten
* `playerID [1-8]`: Spieler-ID, **Index 0 ist ungültig!**
* `buildingType`: [buildings.md](../../api-enums/buildings.md "mention")
* `radius [0-74]`(optional): Radius

#### Rückgabewert

* Gebäude-ID
* 0: Fehler, z.B. wenn die Baustelle hier nicht platziert werden konnte

#### Beispiel

```lua
local buildingID1 = SU.Buildings.AddConstructionSiteEx(100, 100, 1, Buildings.GUARDTOWERSMALL)    // Radius = 24
local buildingID2 = SU.Buildings.AddConstructionSiteEx(100, 100, 1, Buildings.GUARDTOWERSMALL, 10)    // Radius = 10
```
