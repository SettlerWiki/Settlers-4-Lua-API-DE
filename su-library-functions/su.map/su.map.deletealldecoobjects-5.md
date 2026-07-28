---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Map.GetDistanceLineOfSight

## SU.Map.GetDistanceLineOfSight(x1, y1, x2, y2)

Liefert die **Luftlinien**-Distanz zwischen 2 Punkten (die Richtung ist egal).

⇒ siehe auch [su.map.deletealldecoobjects-6.md](su.map.deletealldecoobjects-6.md "mention")

#### Parameter

* `x1,y1`: Koordinaten vom Startpunkt
* `x2,y2`: Koordinaten vom Endpunkt

#### Rückgabewert

* Distanz
* -1 sonst / Fehler

#### Beispiel

```lua
local distanceLineOfSight = SU.Map.GetDistanceLineOfSight(50, 70, 230, 40)
```
