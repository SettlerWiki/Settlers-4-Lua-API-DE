---
description: 'SU Library: ab Version 0.2.0'
---

# SU.Entity.GetPreviousEntityID

## SU.Entity.GetPreviousEntityID(entityID)

Gibt die ID der vorherigen (=**neueren**) Entität relativ der angegebenen Entität vom gleichen Spieler und Typ zurück.

Eine **Entität** ist alles, was im Spiel als "physisches Objekt" vorkommt: d.h. **Objekte, Siedler, Gebäude, Fahrzeuge, Warenstapel, Tiere, etc.**, für Mapper also **quasi alles Auswählbare** (und noch mehr).

#### Parameter

* `entityID`: ID der Entität

#### Rückgabewert

* ID der vorherigen (=neueren) Entität
* 0: sonst / Fehler

#### Beispiel

```lua
local previousID = SU.Entity.GetPreviousEntityID(entityID)
```
