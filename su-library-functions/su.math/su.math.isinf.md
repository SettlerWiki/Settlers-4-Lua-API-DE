---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Math.isInf

## SU.Math.isInf(value)

Überprüft, ob eine Zahl positiv oder negativ unendlich (`inf` oder `-inf`) ist.

#### Parameter

* `value`: `number` – Die zu prüfende Zahl

#### Rückgabewert

* `number` – `1` wenn die Zahl unendlich ist (`inf` oder `-inf`), sonst `0`

#### Beispiel

```lua
local checkInf = SU.Math.isInf(1 / 0)    -- liefert 1
local checkNum = SU.Math.isInf(42)       -- liefert 0
```
