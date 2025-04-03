---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Buildings.SetWorkarea

## SU.Buildings.SetWorkarea(buildingID, x, y)

Setzt für das durch die ID angegebene Gebäude den Arbeitsbereich.

#### Notiz

* x, y können hier beliebig (weit weg) sein, d.h. auf Wasser und auch außerhalb des eigenen Gebiets, wodurch das Gebäude u.U. nicht mehr arbeitet!

#### Parameter

* `buildingID`: ID des Gebäudes
* `x, y`: Koordinaten

#### Rückgabewert

* 1: erfolgreich
* 0: sonst / Fehler (z.B. Koordinaten außerhalb der Karte, Gebäude hat keinen Arbeitsbereich)

#### Beispiel

```lua
local success = SU.Buildings.SetWorkarea(buildingID, 31, 236)
```
