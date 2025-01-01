---
description: 'Neue Funktion: nur mit Settlers United verwendbar!'
---

# Buildings.AddConstructionSiteEx

## `Buildings.AddConstructionSiteEx(x, y, Spieler, Gebäude[, Radius=24])`

Platziert eine Baustelle des angegebenen Gebäude-Typs für den genannten Spieler möglichst nahe an den angegebenen Koordinaten. Dabei wird in einem \[Radius] an Feldern nach einer freien Stelle gesucht, an der die Baustelle platziert werden kann.

Radius (optional): \[0, 74]

#### Rückgabewert

Eindeutige Gebäude-ID oder 0, wenn das Gebäude hier nicht platziert werden konnte

#### Beispiel

```lua
local buildingID1 = Buildings.AddConstructionSiteEx(100,100, 1, Buildings.GUARDTOWERSMALL)    // Radius = 24
local buildingID2 = Buildings.AddConstructionSiteEx(100,100, 1, Buildings.GUARDTOWERSMALL, 10)
```
