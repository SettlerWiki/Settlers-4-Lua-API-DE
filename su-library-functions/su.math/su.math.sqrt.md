---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Math.sqrt

## SU.Math.sqrt(value)

Berechnet die Quadratwurzel einer Zahl.

#### Parameter

* `value`: `number` – Positiv oder Null (größer oder gleich 0)

#### Rückgabewert

* `number` – Die Quadratwurzel
* `nan` (not a number, [su.math.isnan.md](su.math.isnan.md "mention")): Fehler bei negativen Werten

#### Beispiel

```lua
local root = SU.Math.sqrt(16)    -- liefert 4.0
```
