---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Time.GetTotalMinutes

## SU.Time.GetTotalMinutes(floatingPoint=0)

Gibt die Spielzeit in Minuten zurück.

⇒ siehe [su.time.getclockminutes.md](su.time.getclockminutes.md "mention")

#### Parameter

* `floatingPoint` (optional): 0 **abgerundete** Ganzzahl (z.B. 2 Minuten), 1 Gleitkommazahl (z.B. 2,345 Minuten)

#### Rückgabewert

* Vergangene **Minuten** (z.B. 1:**59**:59 Spielzeit **liefert 119m** \[oder 119.99m mit floatingPoint=1], =60 Minuten der vergangenen Stunde + 59 Minuten)
* -1: Fehler

#### Beispiel

```lua
local passedMinutesFloatingPoint = SU.Time.GetTotalMinutes(1)    -- 324.93
local passedMinutes = SU.Time.GetTotalMinutes()    -- 324
```
