---
description: 'Neue Funktion: nur mit Settlers United verwendbar!'
---

# Game.PingPlayer

## `Game.PingPlayer(x, y, playerID[, arrowDuration=15[, minimapDuration=arrowDuration[, msg[, icon=8[, lifetime_s=120[, x, y]]]]]])`

Erzeugt einen Ping **nur für Spieler \[playerID]** auf der Karte und Minimap und gibt optional eine Textnachricht aus, die standardmäßig den Bildschirm zu den Koordinaten `x, y` springen lässt.

Zusätzlich wird ein Sound abgespielt.

`playerID [1, 8]`: siehe [game.localplayer.md](game.localplayer.md "mention"), **Index 0 ist ungültig!**

`arrowDuration` (optional): Zeit in Spiel-Sekunden, wie lange der Pfeil auf der Karte angezeigt werden soll.

`minimapDuration` (optional): Zeit in Spiel-Sekunden, wie lange die blinkende Animation auf der Minimap  angezeigt werden soll.

`[msg, ...]` (optional): siehe [buildings.addbuilding-4.md](buildings.addbuilding-4.md "mention")

## `Game.PingPlayer(x, y, playerID[, msg[, icon=8[, lifetime_s=120[, x, y]]]])`

Gleiche Funktion wie oben, nur mit anderen optionalen Parametern (hier gilt:`arrow- & minimapDuration = 15`).

`[msg, ...]` (optional): siehe [buildings.addbuilding-4.md](buildings.addbuilding-4.md "mention")

#### Rückgabewert

none

#### Beispiel

```lua
Game.PingPlayer(100, 80, 3)    // Ping Spieler 3 an (100, 80) für je 15 Sekunden
Game.PingPlayer(100, 80, 1, 0)    // ... Spieler 1 ohne Pfeil, nur Animation auf der Minimap
Game.PingPlayer(100, 80, 2 "click me")    // ... Spieler 2 mit Textausgabe, Bildschirm springt zu den Koordinaten
Game.PingPlayer(100, 80, 8, 15, 0, "click me")    // ... Spieler 8 nur Pfeil und Nachricht
```
