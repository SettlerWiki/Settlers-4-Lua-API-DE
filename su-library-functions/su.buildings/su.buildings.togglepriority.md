---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Buildings.TogglePriority

## SU.Buildings.TogglePriority(buildingID)

Verändert die Priorisierung der durch die ID angegebenen Baustelle von ein auf aus und umgekehrt.

#### Parameter

* `buildingID`: ID der Baustelle

#### Rückgabewert

* Priorisierungs-Status der Baustelle
* -1: sonst / Fehler

#### Beispiel

```lua
local newPriorityState = SU.Buildings.TogglePriority(buildingID)
```
