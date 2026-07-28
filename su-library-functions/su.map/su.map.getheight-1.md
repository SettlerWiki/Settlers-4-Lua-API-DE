---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Map.GetMousePosition

## SU.Map.GetMousePosition()

Gibt die Position der Maus **des lokalen Spielers** auf der Karte zurück.

**Achtung**: funktioniert nur beim **lokalen Spieler**!\
⇒ **Desync-Gefahr** wenn im Folgenden mit **lokalen Funktionen** das Spiel beeinflusst wird (siehe [place-buildings-1.md](../../tutorials/advanced-tipps/place-buildings-1.md "mention")).

#### Notiz

* Ist die Maus **außerhalb der Karte**, wird die letzte gültige Position zurückgegeben.
* Ist die Maus **außerhalb von S4** (z.B. mehrere Monitore oder Fenstermodus), wird die zuletzt von S4 registrierte Position innerhalb des Fensters zurückgegeben.

#### Rückgabewert

* `x,y`: Koordinaten auf der Karte
* `0,0` oder `-1,-1`: sonst / Fehler

#### Beispiel

```lua
local x, y = SU.Map.GetMousePosition()
```
