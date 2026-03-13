---
description: 'SU Library: ab Version 0.2.0'
---

# SU.Buildings.ToggleHalt

## SU.Buildings.ToggleHalt(buildingID)

Verändert die Pausierung des durch die ID angegebenen Gebäudes von ein auf aus und umgekehrt.

Um den Status direkt zu setzen, verwende [su.buildings.sethaltedstate.md](su.buildings.sethaltedstate.md "mention").

#### Parameter

* `buildingID`: ID des Gebäudes

#### Rückgabewert

* Pausierungs-Status des Gebäudes (0 pausiert)
* -1: sonst / Fehler

#### Beispiel

```lua
local newHaltState = SU.Buildings.ToggleHalt(buildingID)
```
