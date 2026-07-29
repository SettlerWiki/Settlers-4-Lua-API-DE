---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Time.GetClockSeconds

## SU.Time.GetClockSeconds()

Gibt die Sekundenanzahl **der Uhr** rechts oben zurück.

⇒ siehe [su.time.gettotalseconds.md](su.time.gettotalseconds.md "mention")

#### Rückgabewert

* **Sekunden**anzahl der Uhr (z.B. 1:59:**59** Spielzeit **liefert 59**)
* -1: Fehler

#### Beispiel

```lua
local clockSeconds = SU.Time.GetClockSeconds()
```
