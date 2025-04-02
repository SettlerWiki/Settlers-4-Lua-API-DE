---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Buildings.AddConstructionSite

## SU.Buildings.AddConstructionSite(x, y, playerID, buildingType)

Platziert eine Baustelle des angegebenen Gebäude-Typs für den genannten Spieler möglichst nahe an den angegebenen Koordinaten. Dabei wird in einem Radius von 4 Feldern nach einer freien Stelle gesucht, an der die Baustelle platziert werden kann.

⇒ Radius: siehe [buildings.addbuilding-3.md](buildings.addbuilding-3.md "mention")

#### Parameter

* `x, y`: Koordinaten
* `playerID [1-8]`: Spieler-ID, **Index 0 ist ungültig!**
* `buildingType`: [buildings.md](../../api-enums/buildings.md "mention")

#### Rückgabewert

* Gebäude-ID
* 0: Fehler, z.B. wenn die Baustelle hier nicht platziert werden konnte

#### Beispiel

```lua
local buildingID = SU.Buildings.AddConstructionSite(100, 100, 1, Buildings.GUARDTOWERSMALL)
```
