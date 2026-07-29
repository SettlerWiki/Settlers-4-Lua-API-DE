---
description: 'SU Library: ab Version 0.2.0'
---

# SU.Buildings.GetConstructionState

## SU.Buildings.GetConstructionState(buildingID)

Gibt den Gebäude-Status des Gebäudes mit der angegebenen ID zurück.

#### Parameter

* `buildingID`: ID des Gebäudes

#### Rückgabewert

* Buildings.UNDERCONSTRUCTION (siehe [buildings.md](../../api-enums/buildings.md "mention"), =0): das Gebäude ist noch eine Baustelle
* Buildings.READY (=1): das Gebäude ist fertiggestellt
* -1: sonst / Fehler

#### Beispiel

```lua
local buildingState = SU.Buildings.GetConstructionState(buildingID)
```
