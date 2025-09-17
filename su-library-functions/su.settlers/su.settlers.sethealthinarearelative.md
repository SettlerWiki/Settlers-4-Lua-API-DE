---
description: 'SU Library: erst ab Version 0.6.0 verfügbar!'
---

# SU.Settlers.SetHealthInAreaRelative

## SU.Settlers.SetHealthInAreaRelative(playerId, settlerType, x, y, radius, relativeHealth)

Setzt die relativen Lebenspunkte der angegebenen Siedler im gegebenen Bereich.

#### Notiz

* Haben Siedler keine Lebenspunkte (=0), werden sie ignoriert
* Der gegebene Absolutwert (`newHealth`) wird auf die maximalen Lebenspunkte der Entität beschränkt
* `newHealth=0` setzt die Lebenspunkte zwar auf 0, löst aber **nicht** die Kill-Funktion aus (Siedler ist danach quasi 1-Hit)
* `x`, `y`, `radius` oder `newHealth` im negativen Bereich (<0) wird ignoriert und die Funktion nicht ausgeführt (siehe Rückgabewert)

#### Parameter

* `playerId`: ID des Spielers (1-8), Index 0 ungültig, -1 für alle Spieler
* `settlerType`: [settlers.md](../../api-enums/settlers.md "mention") , -1 für alle Siedler
* `x`: x-Koordinate des Bereichs
* `y`: y-Koordinate des Bereichs
* `radius`: Radius des Bereichs
* `relativeHealth`: neue relativen Lebenspunkte (siehe Notizen)

#### Rückgabewert

* Anzahl an Entitäten, dessen Lebenspunkte verändert wurden
* -1: sonst / Fehler

#### Beispiel

```lua
 local amount = SU.Settlers.SetHealthInAreaRelative(playerId, settlerType, x, y, radius, relativeHealth)

 local amount = SU.Settlers.SetHealthInAreaRelative(-1, -1, 217, 125, 20, 90)
 -- Alle Siedler aller Spieler werden in den Bereich auf 90% der max HP gesetzt
 if amount > 0 then
	dbg.stm(amount) -- Anzahl der betroffenen Siedler
 end
```
