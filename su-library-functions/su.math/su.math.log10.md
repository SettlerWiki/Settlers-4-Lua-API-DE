---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Math.log10

## SU.Math.log10(value)

Gibt den dekadischen Logarithmus (Logarithmus zur Basis 10) zurück.

#### Parameter

* `value`: `number` – Positive reelle Zahl (größer als 0)

#### Rückgabewert

* `number` – Der Logarithmus zur Basis 10
* `-inf` ([su.math.isinf.md](su.math.isinf.md "mention")): Bei Eingabe von 0
* `nan` (not a number, [su.math.isnan.md](su.math.isnan.md "mention")): Bei negativen Eingaben

#### Beispiel

```lua
local log10Value = SU.Math.log10(100)    -- liefert 2.0
```
