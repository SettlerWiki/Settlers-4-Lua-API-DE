---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Entity.IsSelected

## SU.Entity.IsSelected(entityID)

Gibt zurück, ob die angegebene Entität aktuell **vom lokalen Spieler** ausgewählt ist.

**Achtung**: funktioniert nur beim **lokalen Spieler**!\
⇒ **Desync-Gefahr** wenn im Folgenden mit **lokalen Funktionen** das Spiel beeinflusst wird (siehe [place-buildings-1.md](../../tutorials/advanced-tipps/place-buildings-1.md "mention")).

Eine **Entität** ist alles, was im Spiel als "physisches Objekt" vorkommt: d.h. **Objekte, Siedler, Gebäude, Fahrzeuge, Warenstapel, Tiere, etc.**, für Mapper also **quasi alles Auswählbare** (und noch mehr).

#### Parameter

* `entityID`: ID der Entität

#### Rückgabewert

* 1: ausgewählt
* 0: sonst / Fehler

#### Beispiel

```lua
local isSelected = SU.Entity.IsSelected(entityID)
```
