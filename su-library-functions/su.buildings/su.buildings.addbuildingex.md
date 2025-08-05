---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Buildings.AddBuildingEx

## SU.Buildings.AddBuildingEx(x, y, playerID, buildingType\[, radius=24\[, externalTowers=0]]

Platziert ein Gebäude des angegebenen Gebäude-Typs für den genannten Spieler möglichst nahe an den angegebenen Koordinaten. Dabei wird im gegebenen Radius nach einer freien Stelle gesucht, an der das Gebäude platziert werden kann.

Diese Funktion behebt das Fehlverhalten der originalen S4-Funktion `Buildings.AddBuildingEx(...)`, die dieses Verhalten eigentlich haben sollte.

#### Notiz

* diese Funktion prüft z.Z. **nicht**, ob Siedler im Weg stehen. **D.h., wird ein Gebäude mit dieser Funktion an einer Stelle platziert, an der Siedler stehen, stürzt das Spiel ab**, da die Siedler im Gebäude gefangen werden und feststecke&#x6E;**!** Eine Lösung ist in Arbeit...\
  ⇒ D.h. **diese Funktion** sollte **nur ganz zu Beginn des Spieles verwendet** werden, wenn noch keine/kaum Siedler in der Map verteilt sind!\
  ⇒ **Der sicherste Weg** ist es, statt Gebäuden **Baustellen zu platzieren**. Diese können nämlich auch über Siedler gesetzt werden kann (siehe [su.buildings.addconstructionsiteex.md](su.buildings.addconstructionsiteex.md "mention")).

#### Parameter

* `x, y`: Koordinaten
* `playerID [1-8]`: Spieler-ID, **Index 0 ist ungültig!**
* `buildingType`: [buildings.md](../../api-enums/buildings.md "mention")
* `radius [0-74]`(optional): Radius
* `externalTowers [0-1]`(optional): bei 1 werden Militärgebäude nur außerhalb des eigenen Landes platziert, um dieses größtmöglich zu erweitern.

#### Rückgabewert

* Gebäude-ID
* 0: Fehler, z.B. wenn das Gebäude hier nicht platziert werden konnte

#### Beispiel

```lua
local buildingID1 = SU.Buildings.AddBuildingEx(100,100, 1, Buildings.GUARDTOWERSMALL)    // Radius = 24
local buildingID2 = SU.Buildings.AddBuildingEx(100,100, 1, Buildings.GUARDTOWERSMALL, 10)    // Radius = 10
```
