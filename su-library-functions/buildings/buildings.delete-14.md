---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Buildings.StoreGood

## SU.Buildings.StoreGood(buildingID, goodType, enable)

Setzt die angegebene Ware beim entsprechenden Gebäude auf "ein-/auszulagern".

#### Parameter

* `buildingID`: ID des Gebäudes
* `goodType`: [goods.md](../../api-enums/goods.md "mention")
* `enable [0-1]`: 0 die Ware wird nicht mehr eingelagert, 1 sie wird jetzt eingelagert

#### Rückgabewert

* 1: erfolgreicher Aufruf (dies bedeutet nur, dass die Parameter valide waren und nicht zwingend, dass der Auftrag ausgeführt wird, z.B. wenn das Gebäude diese Ware nicht einlagern kann!)
* 0: sonst / Fehler

#### Beispiel

```lua
local success = SU.Buildings.StoreGood(buildingID, Goods.MEAT, 1)
```
