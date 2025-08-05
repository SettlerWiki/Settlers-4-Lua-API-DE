---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Buildings.GetHaltedState

## SU.Buildings.GetHaltedState(buildingID)

Gibt zurück, ob das Gebäude mit der angegebenen ID pausiert ist oder nicht.

#### Parameter

* `buildingID`: ID des Gebäudes

#### Rückgabewert

* 1: Gebäude ist pausiert
* 0: sonst / Fehler

#### Beispiel

```lua
local buildingHalted = SU.Buildings.GetHaltedState(buildingID)
```
