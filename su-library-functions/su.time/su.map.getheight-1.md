---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Time.GetClockMinutes

## SU.Time.GetClockMinutes(floatingPoint=0)

Gibt die Minutenanzahl **der Uhr** rechts oben zurück

⇒ siehe [su.map.getheight-4.md](su.map.getheight-4.md "mention")

#### Parameter

* `floatingPoint` (optional): 0 **abgerundete** Ganzzahl (z.B. 2 Minuten), 1 Gleitkommazahl (z.B. 2,345 Minuten)

#### Rückgabewert

* **Minuten**anzahl der Uhr (z.B. 1:**59**:59 Spielzeit **liefert 59** \[oder 59.99 mit floatingPoint=1])
* -1: Fehler

#### Beispiel

```lua
local passedMinutesFloatingPoint = SU.Time.GetClockMinutes(1)    -- 324.93
local passedMinutes = SU.Time.GetClockMinutes()    -- 324
```
