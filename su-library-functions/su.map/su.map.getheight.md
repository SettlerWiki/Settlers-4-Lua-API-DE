---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Map.GetHeight

## SU.Map.GetHeight(x, y)

Gibt die Höhe des Landes an den angegebenen Koordinaten zurück.

#### Parameter

* `x, y`: Koordinaten

#### Rückgabewert

* Höhe des Landes \[0-225]
* 0: Wasser / Fehler

#### Beispiel

```lua
local height = SU.Map.GetHeight(x, y)
```
