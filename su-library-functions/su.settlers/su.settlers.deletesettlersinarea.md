---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Settlers.DeleteSettlersInArea

## SU.Settlers.DeleteSettlersInArea(playerID, settlerType, x, y, radius, skipInhabitants=1)

Entfernt alle Siedler im angegebenen Bereich.

#### Parameter

* `playerID`: ID des Spielers (1-8), Index 0 ungültig, -1 wenn keine Spieler gefiltert werden sollen
* `settlerType`: [settlers.md](../../api-enums/settlers.md "mention")
* `x, y`: Koordinaten
* `radius [0-74]`: Radius
* `skipInhabitants` (optional): ob Insassen (Soldaten) beachtet werden sollen oder nicht. Arbeiter werden immer berücksichtigt!

#### Beispiel

```lua
-- entfernt vom Spieler 1 alle Siedler an 320,170 im Radius von 15
SU.Settlers.DeleteSettlersInArea(1, -1, 320, 170, 15)
```
