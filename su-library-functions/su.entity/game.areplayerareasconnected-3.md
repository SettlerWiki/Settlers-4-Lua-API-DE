---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Entity.GetHealth

## SU.Entity.GetHealth(entityID)

Gibt die aktuellen Lebenspunkte der angegebenen Entität zurück.

Eine **Entität** ist alles, was im Spiel als "physisches Objekt" vorkommt: d.h. **Objekte, Siedler, Gebäude, Fahrzeuge, Warenstapel, Tiere, etc.**, für Mapper also **quasi alles Auswählbare** (und noch mehr).

#### Notiz

* Macht natürlich **nur Sinn für Entitäten mit Lebenspunkten**...

#### Parameter

* `entityID`: ID der Entität

#### Rückgabewert

* Lebenspunkte

#### Beispiel

```lua
local health = SU.Entity.GetHealth(entityID)
```
