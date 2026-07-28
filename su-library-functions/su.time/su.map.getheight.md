---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Time.GetClockHours

## SU.Time.GetClockHours(floatingPoint=0)

Gibt die Stundenanzahl **der Uhr** rechts oben zurück

⇒ siehe [su.map.getheight-3.md](su.map.getheight-3.md "mention")

#### Parameter

* `floatingPoint` (optional): 0 **abgerundete** Ganzzahl (z.B. 2 Stunden), 1 Gleitkommazahl (z.B. 2,345 Stunden)

#### Rückgabewert

* **Stunden**anzahl der Uhr (z.B. **1**:59:59 Spielzeit **liefert 1** \[oder 1.99 mit floatingPoint=1])
* -1: Fehler

#### Beispiel

```lua
local clockHoursFloatingPoint = SU.Time.GetClockHours(1)    -- 3.93
local clockHours = SU.Time.GetClockHours()    -- 3
```
