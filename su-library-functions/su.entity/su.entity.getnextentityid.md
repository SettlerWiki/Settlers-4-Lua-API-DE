---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Entity.GetNextEntityID

## SU.Entity.GetNextEntityID(entityID)

Gibt die ID der nächste (=neuere) Entität relativ der angegebenen Entität vom gleichen Spieler und Typ zurück.

Eine **Entität** ist alles, was im Spiel als "physisches Objekt" vorkommt: d.h. **Objekte, Siedler, Gebäude, Fahrzeuge, Warenstapel, Tiere, etc.**, für Mapper also **quasi alles Auswählbare** (und noch mehr).

#### Parameter

* `entityID`: ID der Entität

#### Rückgabewert

* ID der nächsten (=neuer) Entität
* 0: sonst / Fehler

#### Beispiel

```lua
local nextID = SU.Entity.GetNextEntityID(entityID)
```
