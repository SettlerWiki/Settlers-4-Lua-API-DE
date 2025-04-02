---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Buildings.SetTradingRoute

## SU.Buildings.SetTradingRoute(srcBuildingID, dstBuildingID)

Setzt eine Handelsroute vom einen zum anderen Handels-Gebäude (Hafen, Marktplatz).

#### Parameter

* `srcBuildingID`: ID des Start-Gebäudes
* `dstBuildingID`: ID des Ziel-Gebäudes

#### Rückgabewert

* 1: erfolgreicher Aufruf
* 0: sonst / Fehler

#### Beispiel

```lua
local success = SU.Buildings.SetTradingRoute(srcBuildingID, dstBuildingID)
```
