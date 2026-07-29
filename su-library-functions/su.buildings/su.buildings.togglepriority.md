---
description: 'SU Library: ab Version 0.2.0'
---

# SU.Buildings.TogglePriority

## SU.Buildings.TogglePriority(buildingID)

Verändert die Priorisierung der durch die ID angegebenen Baustelle von ein auf aus und umgekehrt.

Um den Status direkt zu setzen, verwende [su.buildings.setprioritystate.md](su.buildings.setprioritystate.md "mention").

#### Parameter

* `buildingID`: ID der Baustelle

#### Rückgabewert

* Priorisierungs-Status der Baustelle (1 priorisiert)
* -1: sonst / Fehler

#### Beispiel

```lua
local newPriorityState = SU.Buildings.TogglePriority(buildingID)
```
