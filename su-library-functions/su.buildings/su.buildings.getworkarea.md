---
description: 'SU Library: erst ab Version 0.6.0 verfügbar!'
---

# SU.Buildings.GetWorkarea

## SU.Buildings.GetWorkarea(buildingID)

Gibt die Koordinaten zurück, wo der Arbeitsbereich des Gebäudes gesetzt ist.

#### Parameter

* `buildingID`: ID des Gebäudes

#### Rückgabewert

* x, y: Koordinaten des Arbeitsbereich
* -1: sonst / Fehler

#### Beispiel

```lua
local x, y = SU.Buildings.GetWorkarea(buildingID)
```
