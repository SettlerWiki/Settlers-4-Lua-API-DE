---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Game.GetBeds

## SU.Game.GetBeds(playerID, mode=0)

Gibt die Anzahl der Betten zurück.

#### Parameter

* `playerID [1-8]`: Spieler-ID, **Index 0 ist ungültig!**
* `mode` (optional): 0 Gesamtanzahl, 1 Startbettenanzahl (ohne Wohnhäuser), 2 Bettenanzahl nur von Wohnhäusern

#### Rückgabewert

* Bettenanzahl
* -1 sonst / Fehler

#### Beispiel

```lua
local numBeds = SU.Game.GetBeds(1, 1)    -- so viele Betten hat Spieler 1 *ohne* Wohnhäuser
local numBeds = SU.Game.GetBeds(1, 2)    -- so viele Betten hat Spieler 1 durch Wohnhäuser
local numBeds = SU.Game.GetBeds(1)    -- so viele Betten hat Spieler 1 insgesamt
```
