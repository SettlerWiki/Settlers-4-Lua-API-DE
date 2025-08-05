---
description: 'SU Library: erst ab Version 0.3.0 verfügbar!'
---

# SU.Goods.AddPileEx

## SU.Goods.AddPileEx(x, y, goodType, amount)

Fügt **beliebig viele** Waren des angegebenen Waren-Typs um die Koordinaten hinzu, und erstellt automatisch entsprechend viele Warenstapel.

#### Parameter

* `x, y`: Koordinaten
* `goodType`: [goods.md](../../api-enums/goods.md "mention")
* `amount`: Anzahl an hinzuzufügenden Waren

#### Beispiel

```lua
SU.Goods.AddPileEx(151, 22, Goods.SWORD, 80)    -- adds 80 swords
```
