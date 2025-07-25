---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Game.IsCurrentlyOnScreen

## SU.Game.IsCurrentlyOnScreen(guiElement)

Überprüft, ob das angegebene GUI-Element aktuell am Bildschirm des lokalen Spielers ist.

#### Notiz

* da das Lua-Skript nur direkt im Spiel und nicht in den Menüs davor läuft, machen nur alle "SU.GUIElements.**MENU**\_XXX" Variablen Sinn.

#### Parameter

* `guiElement`: [ai-6.md](../../su-api-enums/ai-6.md "mention")

#### Rückgabewert

* 1: `guiElement` ist am Bildschirm
* 0: sonst / Fehler

#### Beispiel

```lua
local isOnScreen = SU.Game.IsCurrentlyOnScreen(SU.GUIElements.MENU_BUILDINGS_FOOD)
```
