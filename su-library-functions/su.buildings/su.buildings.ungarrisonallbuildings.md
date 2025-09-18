---
description: 'SU Library: erst ab Version 0.6.0 verfügbar!'
---

# SU.Buildings.UnGarrisonAllBuildings

## SU.Buildings.UnGarrisonAllBuildings(playerID, smallTowers, bigTowers, castles)

Setzt alle angegebenen Gebäude vom Spieler auf "zu verlassen".

#### Notiz

* Diese Funktion ist ein Net-Event, d.h. sie sollte **nicht zu oft** aufgerufen werden!

#### Parameter

* `playerID [1-8]`: Spieler-ID, **Index 0 ist ungültig!**
* `smallTowers [0, 1]`: 1 um kleine Türme zu verlassen.
* `bigTowers [0, 1]`: 1 um große Türme zu verlassen.
* `castles [0, 1]`: 1 um Burgen zu verlassen.

#### Rückgabewert

none

#### Beispiel

```lua
-- leert nur alle großen Türme vom Spieler 3
SU.Buildings.UnGarrisonAllWarriors(3, 0, 1, 0)
```
