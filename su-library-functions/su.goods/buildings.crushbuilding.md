---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Goods.DeleteGoodsInArea

## SU.Goods.DeleteGoodsInArea(goodType, x, y, radius, playerID=-1)

Löscht Waren im angegebenen Bereich.

#### Parameter

* `goodType`: [goods.md](../../api-enums/goods.md "mention"), -1 wenn keine Waren gefiltert werden sollen
* `x, y`: Koordinaten
* `radius [0-74]`: Radius
* `playerID`: ID des Spielers (1-8), Index 0 ungültig, -1 wenn keine Spieler gefiltert werden sollen

#### Beispiel

```lua
-- löscht alle Waren von Spieler 1 im angegebenen Bereich
SU.Buildings.DeleteGoodsInArea(-1, 320, 170, 15, 1)
```
