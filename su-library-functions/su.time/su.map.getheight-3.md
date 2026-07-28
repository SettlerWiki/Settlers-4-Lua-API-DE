---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Time.GetTotalHours

## SU.Time.GetTotalHours(floatingPoint=0)

Gibt die Spielzeit in Stunden zurück.

⇒ siehe [su.map.getheight.md](su.map.getheight.md "mention")

#### Parameter

* `floatingPoint` (optional): 0 **abgerundete** Ganzzahl (z.B. 2 Stunden), 1 Gleitkommazahl (z.B. 2,345 Stunden)

#### Rückgabewert

* Vergangene Stunden (z.B. 1:59:59 Spielzeit **liefert 1** \[oder 1.99 mit floatingPoint=1])
* -1: Fehler

#### Beispiel

```lua
local passedHoursFloatingPoint = SU.Time.GetTotalHours(1)    -- 3.93
local passedHours = SU.Time.GetTotalHours()    -- 3
```
