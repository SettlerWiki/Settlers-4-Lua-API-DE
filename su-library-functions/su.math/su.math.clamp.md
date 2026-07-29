---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Math.clamp

## SU.Math.clamp(value, min, max)

Begrenzt eine Zahl auf ein angegebenes Intervall zwischen einem Minimum und einem Maximum.

#### Parameter

* `value`: `number` – Der einzuschränkende Wert
* `min`: `number` – Untere Grenze (inklusive)
* `max`: `number` – Obere Grenze (inklusive)

#### Rückgabewert

* `number` – `min`, falls `value < min`; `max`, falls `value > max`; sonst `value`

#### Beispiel

```lua
local clamped = SU.Math.clamp(15, 0, 10)    -- liefert 10
```
