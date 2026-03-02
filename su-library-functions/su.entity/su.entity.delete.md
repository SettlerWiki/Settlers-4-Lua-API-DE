---
description: 'SU Library: ab Version 0.6.4'
---

# SU.Entity.Delete

## SU.Entity.Delete(entityID)

Löscht/Zerstört die angegebene Entität (**beschränkt** auf: Gebäude, Siedler, Schiffe und Fahrzeuge).

Eine **Entität** ist alles, was im Spiel als "physisches Objekt" vorkommt: d.h. **Objekte, Siedler, Gebäude, Fahrzeuge, Warenstapel, Tiere, etc.**, für Mapper also **quasi alles Auswählbare** (und noch mehr).



#### Welche Funktion genau brauche ich?

Ist die Entität mit der `entityID`:

* **generell** ein Gebäude, Siedler, Warenstapel, etc., **egal welches/r genau**\
  ⇒ [su.entity.getentitytype.md](su.entity.getentitytype.md "mention") ([su.entity.getbasetype.md](su.entity.getbasetype.md "mention"), [su.entity.getclass.md](su.entity.getclass.md "mention"))
* **grob gruppiert** ein Nahrungsgebäude, eine Mine, ein Soldat\
  ⇒ [su.entity.getroleclass.md](su.entity.getroleclass.md "mention")
* **spezifisch** eine Kaserne, ein Bogenschütze, ein Goldbarren, etc.\
  ⇒ [su.entity.gettype.md](su.entity.gettype.md "mention")



#### Parameter

* `entityID`: ID der Entität

#### Rückgabewert

* 1: erfolgreich gelöscht/zerstört
* 0: Fehler: ungültige ID
* -1: Fehler: gültige ID, konnte aber nicht gelöscht/zerstört werden

#### Beispiel

```lua
local success = SU.Entity.Delete(entityID)
```
