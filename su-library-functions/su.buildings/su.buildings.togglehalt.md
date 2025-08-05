---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Buildings.ToggleHalt

## SU.Buildings.ToggleHalt(buildingID)

Verändert die Pausierung des durch die ID angegebenen Gebäudes von ein auf aus und umgekehrt.

#### Parameter

* `buildingID`: ID des Gebäudes

#### Rückgabewert

* Pausierungs-Status des Gebäudes
* -1: sonst / Fehler

#### Beispiel

```lua
local newHaltState = SU.Buildings.ToggleHalt(buildingID)
```
