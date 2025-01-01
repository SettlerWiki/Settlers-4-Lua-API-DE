---
description: VERALTET und FEHLERHAFT
---

# Buildings.AddBuilding

## ~~`Buildings.AddBuilding(x, y, Spieler, Gebäude)`~~

**Diese Funktion sollte NICHT mehr verwendet werden (siehe unten).**\
**Stattdessen ⇒** [buildings.addbuilding-1.md](buildings.addbuilding-1.md "mention")

Platziert ein Gebäude für den genannten Spieler an den angegebenen Koordinaten.

**Achtung:** durch **fehlerhaftes Verhalten** wird das Gebäude platziert, auch wenn die Stelle eigentlich blockiert ist.\
**Achtung:** zusätzlich **stürzt das Spiel ab**, wenn sich an dieser Stelle bereits Siedler befinden, da diese dadurch danach bewegungsunfähig sind.\
&#xNAN;**⇒ Diese Funktion sollte - wenn überhaupt - nur am Anfang im Script stehen**, wo noch keine Siedler und Warenstapel existieren / platziert wurden und später nicht mehr verwendet werden!

Sie funktioniert noch wie bisher, um Rückwärtskompatibilität zu gewährleisten.

#### Rückgabewert

Eindeutige Gebäude-ID

#### Beispiel

```lua
Buildings.AddBuilding(100,100, 1, Buildings.GUARDTOWERSMALL)
```
