---
description: 'SU Library: ab Version 0.2.0'
---

# SU.Buildings.GetConstructionState

## SU.Buildings.GetConstructionState(buildingID)

Gibt den Gebäude-Status des Gebäudes mit der angegebenen ID zurück.

#### Parameter

* `buildingID`: ID des Gebäudes

#### Rückgabewert

* SU.Buildings.UNDERCONSTRUCTION: das Gebäude ist noch eine Baustelle
* SU.Buildings.READY: das Gebäude ist fertiggestellt
* -1: sonst / Fehler

#### Beispiel

```lua
local buildingState = SU.Buildings.GetConstructionState(buildingID)
```
