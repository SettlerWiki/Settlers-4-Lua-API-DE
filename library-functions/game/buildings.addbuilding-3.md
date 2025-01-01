---
description: 'Neue Funktion: nur mit Settlers United verwendbar!'
---

# Game.Ping

## `Game.Ping(x, y[, arrowDuration=15[, minimapDuration=arrowDuration[, msg[, icon=8[, lifetime_s=120[, x, y]]]]]])`

Erzeugt einen Ping **für alle Spieler** auf der Karte und Minimap und gibt optional eine Textnachricht aus, die standardmäßig den Bildschirm zu den Koordinaten `x, y` springen lässt.

Zusätzlich wird ein Sound abgespielt.

`arrowDuration` (optional): Zeit in Spiel-Sekunden, wie lange der Pfeil auf der Karte angezeigt werden soll.

`minimapDuration` (optional): Zeit in Spiel-Sekunden, wie lange die blinkende Animation auf der Minimap  angezeigt werden soll.

`[msg, ...]` (optional) : siehe [buildings.addbuilding-7.md](buildings.addbuilding-7.md "mention")

## `Game.Ping(x, y[, msg[, icon=8[, lifetime_s=120[, x, y]]]])`

Gleiche Funktion wie oben, nur mit anderen optionalen Parametern (hier gilt:`arrow- & minimapDuration = 15`).

`[msg, ...]` (optional): siehe [buildings.addbuilding-7.md](buildings.addbuilding-7.md "mention")

#### Rückgabewert

none

#### Beispiel

```lua
Game.Ping(100, 80)    // Ping an (100, 80) für je 15 Sekunden
Game.Ping(100, 80, 0)    // ... ohne Pfeil, nur Animation auf der Minimap (und Sound)
Game.Ping(100, 80, "click me")    // ... mit Textausgabe, Bildschirm springt zu den Koordinaten
Game.Ping(100, 80, 15, 0, "click me")    // ... nur Pfeil und Nachricht
```
