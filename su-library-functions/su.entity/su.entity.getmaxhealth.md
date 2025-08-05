---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Entity.GetMaxHealth

## SU.Entity.GetMaxHealth(entityID)

Gibt die maximalen Lebenspunkte der angegebenen Entität zurück.

Eine **Entität** ist alles, was im Spiel als "physisches Objekt" vorkommt: d.h. **Objekte, Siedler, Gebäude, Fahrzeuge, Warenstapel, Tiere, etc.**, für Mapper also **quasi alles Auswählbare** (und noch mehr).

#### Notiz

* Liefert **nur bei Siedlern** richtige / sinnvolle Ergebnisse!

#### Parameter

* `entityID`: ID der Entität

#### Rückgabewert

* Lebenspunkte

#### Beispiel

```lua
local maxHealth = SU.Entity.GetMaxHealth(entityID)
```
