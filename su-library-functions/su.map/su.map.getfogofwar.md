---
description: 'SU Library: ab Version 0.2.0'
---

# SU.Map.GetFogOfWar

## SU.Map.GetFogOfWar(x, y)

Gibt das Level des Nebels des Krieges (wie verdeckt das Land für den lokalen Spieler ist) an den angegebenen Koordinaten zurück.

#### Parameter

* `x, y`: Koordinaten

#### Rückgabewert

* Level des Nebels des Krieges
  * 0: komplett sichtbar
  * 63: komplett schwarz

#### Beispiel

```lua
local fogOfWar = SU.Map.GetFogOfWar(x, y)
```
