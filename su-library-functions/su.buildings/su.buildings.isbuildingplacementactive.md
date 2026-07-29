---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Buildings.IsBuildingPlacementActive

## SU.Buildings.IsBuildingPlacementActive()

Zeigt an, ob gerade die Gebäude-Platzierung aktiviert ist, nachdem ein Gebäude im Menü/per Hotkey ausgewählt wurde (siehe auch [su.buildings.getactivebuildingplacement.md](su.buildings.getactivebuildingplacement.md "mention")).

#### Rückgabewerte

* 1: Gebäude-Platzierung ist aktiv
* 0: sonst / Fehler

#### Beispiel

```lua
local isActive = SU.Buildings.IsBuildingPlacementActive()
```
