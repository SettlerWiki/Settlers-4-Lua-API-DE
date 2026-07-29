---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Time.GetTotalSeconds

## SU.Time.GetTotalSeconds()

Gibt die Spielzeit in Sekunden zurück.

⇒ siehe [su.time.getclockseconds.md](su.time.getclockseconds.md "mention")

#### Rückgabewert

* Vergangene Sekunden (z.B. 0:04:59 Spielzeit **liefert 299s** (=4m\*60+59s)), hh:mm:ss
* -1: Fehler

#### Beispiel

```lua
local passedSeconds = SU.Time.GetTotalSeconds()
```
