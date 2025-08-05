---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Buildings.GetPriorityState

## SU.Buildings.GetPriorityState(buildingID)

Gibt zurück, ob die Baustelle mit der angegebenen ID priorisiert ist oder nicht.

#### Parameter

* `buildingID`: ID der Baustelle

#### Rückgabewert

* 1: Baustelle ist priorisiert
* 0: sonst / Fehler

#### Beispiel

```lua
local priorityState = SU.Buildings.GetPriorityState(buildingID)
```
