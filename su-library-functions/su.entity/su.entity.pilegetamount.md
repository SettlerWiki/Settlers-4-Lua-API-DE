---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Entity.PileGetAmount

## SU.Entity.PileGetAmount(entityID)

Gibt die Anzahl an Waren innerhalb des angegebenen Warenstapels zurück.

Eine **Entität** ist alles, was im Spiel als "physisches Objekt" vorkommt: d.h. **Objekte, Siedler, Gebäude, Fahrzeuge, Warenstapel, Tiere, etc.**, für Mapper also **quasi alles Auswählbare** (und noch mehr).

#### Parameter

* `entityID`: ID der Entität

#### Rückgabewert

* Anzahl

#### Beispiel

```lua
local pileAmount = SU.Entity.PileGetAmount(entityID)
```
