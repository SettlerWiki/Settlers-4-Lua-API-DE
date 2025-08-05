---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Map.GetEcoSector

## SU.Map.GetEcoSector(x, y)

Gibt den Wirtschaftssektor an den gegebenen Koordinaten zurück.

#### Parameter

* `x, y`: Koordinaten

#### Rückgabewert

* Eindeutige ID des Wirtschaftssektors
* 0: sonst (Koordinaten sind in keinem Wirtschaftssektor) / Fehler

#### Beispiel

```lua
local ecoSector = SU.Map.GetEcoSector(x, y)
```
