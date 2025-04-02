---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Buildings.SetHaltedState

## SU.Buildings.SetHaltedState(buildingID, haltedState)

Setzt das durch die ID angegebene Gebäude entsprechenden auf (nicht) pausiert.

#### Parameter

* `buildingID`: ID des Gebäudes
* `haltedState [0-1]`: 0 um das Gebäude arbeiten zu lassen, 1 um es zu pausieren

#### Rückgabewert

* 1: Gebäude ist nun pausiert oder war es schon
* 0: sonst / Fehler

#### Beispiel

```lua
local newHaltedState = SU.Buildings.SetHaltedState(buildingID, 1)    // pausiert das Gebäude
```
