---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Map.GetOwner

## SU.Map.GetOwner(x, y)

Gibt die Spieler-ID desjenigen zurück, der die angegebenen Koordinaten besitzt.

#### Parameter

* `x, y`: Koordinaten

#### Rückgabewert

* playerID \[1-8]: Spieler-ID, dem das Land gehört
* 0: sonst / Fehler

#### Beispiel

```lua
local owner = SU.Map.GetOwner(x, y)
```
