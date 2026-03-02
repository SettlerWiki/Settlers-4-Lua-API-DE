---
description: 'SU Library: ab Version 0.2.0'
---

# SU.Buildings.TradeGood

## SU.Buildings.TradeGood(buildingID, goodType, amount)

Stellt am durch die ID gegebenen Gebäude ein, wie viel der angegebenen Ware verschickt werden soll.

Die Handelsroute wird mittels [su.buildings.settradingroute.md](su.buildings.settradingroute.md "mention")gesetzt.

#### Parameter

* `buildingID`: ID des Gebäudes
* `goodType`: [goods.md](../../api-enums/goods.md "mention")
* `amount [0-100]`: Anzahl (100=unendlich)

#### Rückgabewert

* 1: Auftrag erfolgreich erteilt
* 0: sonst / Fehler

#### Beispiel

```lua
local success = SU.Buildings.TradeGood(buildingID, Goods.STONE, 100)
```
