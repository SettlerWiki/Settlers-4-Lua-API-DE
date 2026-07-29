---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Math.isNan

## SU.Math.isNan(value)

Überprüft, ob ein Wert "Not a Number" (`nan`) ist.

#### Parameter

* `value`: `number` – Die zu prüfende Zahl

#### Rückgabewert

* `number` – `1` wenn der Wert `nan` ist, sonst `0`

#### Beispiel

```lua
local invalid = SU.Math.sqrt(-1)
local checkNan = SU.Math.isNan(invalid)    -- liefert 1
```
