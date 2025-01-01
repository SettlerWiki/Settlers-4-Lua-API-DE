---
description: 'Neue Funktion: nur mit Settlers United verwendbar!'
---

# Buildings.AddBuildingExSU

## `Buildings.AddBuildingExSU(x, y, Spieler, Gebäude[, Radius=24[,``TürmeAußerhalb=0]])`

Platziert ein Gebäude des angegebenen Gebäude-Typs für den genannten Spieler möglichst nahe an den angegebenen Koordinaten. Dabei wird in einem \[Radius] an Feldern nach einer freien Stelle gesucht, an der die Baustelle platziert werden kann.

Radius (optional): \[0, 74]

TürmeAußerhalb (optional): \[0, 1], wenn 1, dann werden Militärgebäude außerhalb des eigenen Landes platziert, um das Land größtmöglich zu erweitern.

Diese Funktion behebt das Fehlverhalten der originalen S4-Funktion `Buildings.AddBuildingEx(...)`, die dieses Verhalten eigentlich haben sollte.

#### Rückgabewert

Eindeutige Gebäude-ID oder 0, wenn das Gebäude hier nicht platziert werden konnte

#### Beispiel

```lua
local buildingID1 = Buildings.AddBuildingExSU(100,100, 1, Buildings.GUARDTOWERSMALL)    // Radius = 24
local buildingID2 = Buildings.AddBuildingExSU(100,100, 1, Buildings.GUARDTOWERSMALL, 10)
```
