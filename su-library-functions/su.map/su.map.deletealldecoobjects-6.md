---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Map.GetDistancePath

## SU.Map.GetDistancePath(x1, y1, x2, y2)

Liefert die **Weg**-Distanz zwischen 2 Punkten, die ein Siedler brauchen würde um von P1 nach P2 zu gelangen (die Richtung ist egal).

⇒ siehe auch [su.map.deletealldecoobjects-5.md](su.map.deletealldecoobjects-5.md "mention")

#### Parameter

* `x1,y1`: Koordinaten vom Startpunkt
* `x2,y2`: Koordinaten vom Endpunkt

#### Rückgabewert

* Distanz
* -1 sonst / Fehler

#### Beispiel

```lua
local distancePath = SU.Map.GetDistancePath(50, 70, 230, 40)
```
