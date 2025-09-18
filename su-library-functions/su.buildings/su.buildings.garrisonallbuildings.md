---
description: 'SU Library: erst ab Version 0.6.0 verfügbar!'
---

# SU.Buildings.GarrisonAllBuildings

## SU.Buildings.GarrisonAllBuildings(playerID, smallTowers, bigTowers, castles)

Setzt alle angegebenen Gebäude vom Spieler auf "zu besetzen".

#### Notiz

* Diese Funktion ist ein Net-Event, d.h. sie sollte **nicht zu oft** aufgerufen werden!

#### Parameter

* `playerID [1-8]`: Spieler-ID, **Index 0 ist ungültig!**
* `smallTowers [0, 1]`: 1 um kleine Türme zu besetzen.
* `bigTowers [0, 1]`: 1 um große Türme zu besetzen.
* `castles [0, 1]`: 1 um Burgen zu besetzen.

#### Rückgabewert

none

#### Beispiel

```lua
-- besetzt nur alle kleinen Türme vom Spieler 3
SU.Buildings.GarrisonAllWarriors(3, 1, 0, 0)
```
