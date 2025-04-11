---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Game.PingTeam

## SU.Game.Ping(x, y, teamID\[, arrowDuration=15\[, minimapDuration=arrowDuration\[, msg\[, icon=8\[, lifetime\_s=120\[, x2, y2]]]]]])

Erzeugt einen Ping **nur für das angegebene Team** auf der Karte und Minimap und gibt optional eine Textnachricht aus, die standardmäßig den Bildschirm zu den Koordinaten `x, y` springen lässt.

Zusätzlich wird ein Sound abgespielt.

#### Parameter

* `teamID [1-8]`: Team-ID, **Index 0 ist ungültig!**
* `arrowDuration` (optional): Zeit in Spiel-Sekunden, wie lange der Pfeil auf der Karte angezeigt werden soll.
* `minimapDuration` (optional): Zeit in Spiel-Sekunden, wie lange die blinkende Animation auf der Minimap  angezeigt werden soll.
* `[msg, ...]` (optional): siehe [buildings.addbuilding-9.md](buildings.addbuilding-9.md "mention")



## SU.Game.Ping(x, y, teamID\[, msg\[, icon=8\[, lifetime\_s=120\[, x, y]]]])

Gleiche Funktion wie oben, nur mit anderen optionalen Parametern (hier gilt: `arrowDuration=minimapDuration=15`).



#### Beispiel

```lua
SU.Game.PingTeam(100, 80, 3)    // Ping Team 3 an (100, 80) für je 15 Sekunden
SU.Game.PingTeam(100, 80, 1, 0)    // ... Team 1 ohne Pfeil, nur Animation auf der Minimap
SU.Game.PingTeam(100, 80, 2, "click me")    // ... Team 2 mit Textausgabe, Bildschirm springt zu den Koordinaten
SU.Game.PingTeam(100, 80, 8, 15, 0, "click me")    // ... Team 8 nur Pfeil und Nachricht
```
