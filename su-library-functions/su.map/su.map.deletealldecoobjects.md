---
description: 'SU Library: erst ab Version 0.6.2 verfügbar!'
---

# SU.Map.DeleteAllDecoObjects

## SU.Map.DeleteAllDecoObjects(\[onlyBlockingOnes=1])

Entfernt alle Objekte auf der gesamten Karte, standardmäßig nur blockierende, optional wirklich alle.

#### Notiz

* Einige wenige (noch wachsende) Objekte werden z.Z. nicht entfernt.

#### Parameter

* onlyBlockingOnes`[0,1]` (optional): entfernt mit 0 alle Objekte, 1 nur blockierende

#### Beispiel

```lua
SU.Map.DeleteAllDecoObjects()    -- removes blocking objects only
SU.Map.DeleteAllDecoObjects(0)    -- removes all objects, even grass etc
```
