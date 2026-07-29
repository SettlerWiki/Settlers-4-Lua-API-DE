---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Math.log

## SU.Math.log(value, base)

Gibt den natürlichen Logarithmus (Basis e) oder den Logarithmus zu einer optionalen Basis zurück.

#### Parameter

* `value`: `number` – Positive reelle Zahl (größer als 0)
* `base`: `number` _(optional)_ – Basis des Logarithmus (Standard: e)

#### Rückgabewert

* `number` – Der Logarithmus von `value`
* `-inf` ([su.math.isinf.md](su.math.isinf.md "mention")): Bei Eingabe von 0
* `nan` (not a number, [su.math.isnan.md](su.math.isnan.md "mention")): Bei negativen Eingaben

#### Beispiel

```lua
local naturalLog = SU.Math.log(2.71828)    -- liefert ca. 1.0
local customLog  = SU.Math.log(8, 2)        -- liefert ca. 3.0
```
