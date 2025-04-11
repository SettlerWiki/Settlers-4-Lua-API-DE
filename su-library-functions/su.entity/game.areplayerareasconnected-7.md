---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Entity.GetPosition

## SU.Entity.GetPosition(entityID)

Gibt die Position der angegebenen Entität zurück.

Eine **Entität** ist alles, was im Spiel als "physisches Objekt" vorkommt: d.h. **Objekte, Siedler, Gebäude, Fahrzeuge, Warenstapel, Tiere, etc.**, für Mapper also **quasi alles Auswählbare** (und noch mehr).

#### Parameter

* `entityID`: ID der Entität

#### Rückgabewert

* `x, y`: Position
* -1, -1: sonst / Fehler

#### Beispiel

```lua
local x, y = SU.Entity.GetPosition(entityID)
```
