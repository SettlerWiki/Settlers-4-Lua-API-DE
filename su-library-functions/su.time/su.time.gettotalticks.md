---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Time.GetTotalTicks

## SU.Time.GetTotalTicks()

Gibt die Anzahl vergangener Tick zurück (das Spiel läuft intern mit \~14 Ticks pro Sekunde).

#### Rückgabewert

* Vergangene Ticks
* -1: Fehler

#### Beispiel

```lua
local passedTicks = SU.Time.GetTotalTicks()
```
