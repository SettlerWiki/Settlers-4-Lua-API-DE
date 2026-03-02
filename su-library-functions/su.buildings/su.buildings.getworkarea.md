---
description: 'SU Library: ab Version 0.6.0'
---

# SU.Buildings.GetWorkarea

## SU.Buildings.GetWorkarea(buildingID)

Gibt die Koordinaten des Arbeitsbereiches des Gebäudes zurück.

#### Parameter

* `buildingID`: ID des Gebäudes

#### Rückgabewert

* x, y: Koordinaten des Arbeitsbereiches
* -1: sonst / Fehler

#### Beispiel

```lua
local x, y = SU.Buildings.GetWorkarea(buildingID)
```
