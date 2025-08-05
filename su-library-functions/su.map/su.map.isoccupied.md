---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Map.IsOccupied

## SU.Map.IsOccupied(x, y)

Gibt zurück, ob das Gebiet an den angegebenen Koordinaten von jemandem besetzt / eingenommen ist oder nicht.

#### Parameter

* `x, y`: Koordinaten

#### Rückgabewert

* 1: eingenommen
* 0: sonst / Fehler

#### Beispiel

```lua
local isOccupied = SU.Map.IsOccupied(x, y)
```
