---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Game.Ping

## SU.Game.Ping(x, y\[, arrowDuration=15\[, minimapDuration=arrowDuration\[, msg\[, icon=8\[, lifetime\_s=120\[, x2, y2]]]]]])

Erzeugt einen Ping **für alle Spieler** auf der Karte und Minimap und gibt optional eine Textnachricht aus, die standardmäßig den Bildschirm zu den Koordinaten `x, y` springen lässt.

Zusätzlich wird ein Sound abgespielt.

#### Parameter

* `arrowDuration` (optional): Zeit in Spiel-Sekunden, wie lange der Pfeil auf der Karte angezeigt werden soll.
* `minimapDuration` (optional): Zeit in Spiel-Sekunden, wie lange die blinkende Animation auf der Minimap  angezeigt werden soll.
* `[msg, ...]` (optional) : siehe [su.game.showtextmessage.md](su.game.showtextmessage.md "mention")



## SU.Game.Ping(x, y\[, msg\[, icon=8\[, lifetime\_s=120\[, x2, y2]]]])

Gleiche Funktion wie oben, nur mit anderen optionalen Parametern (hier gilt: `arrowDuration=minimapDuration=15`).



#### Beispiel

```lua
SU.Game.Ping(100, 80)    // Ping an (100, 80) für je 15 Sekunden
SU.Game.Ping(100, 80, 0)    // ... ohne Pfeil, nur Animation auf der Minimap (und Sound)
SU.Game.Ping(100, 80, "click me")    // ... mit Textausgabe, Bildschirm springt zu den Koordinaten
SU.Game.Ping(100, 80, 15, 0, "click me")    // ... nur Pfeil und Nachricht
```
