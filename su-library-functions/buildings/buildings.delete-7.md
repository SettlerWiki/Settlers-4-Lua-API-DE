---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Buildings.SetPriorityState

## SU.Buildings.SetPriorityState(buildingID, priorityState)

Setzt die durch die ID angegebene Baustelle entsprechenden auf (nicht) priorisiert.

#### Parameter

* `buildingID`: ID der Baustelle
* `priorityState [0-1]`: 0 um die Baustelle auf normal zu setzen, 1 um sie zu priorisieren

#### Rückgabewert

* 1: Baustelle ist nun priorisiert oder war es schon
* 0: sonst / Fehler

#### Beispiel

```lua
local newPriorityState = SU.Buildings.SetPriorityState(buildingID, 1)    // aktiviert Priorisierung
```
