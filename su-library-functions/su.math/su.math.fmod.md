---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Math.fmod

## SU.Math.fmod(x, y)

Gibt den Rest der **Gleitkomma**division von x / y zurück.

⇒ für **Ganz**zahlen [su.math.mod.md](su.math.mod.md "mention")

#### Parameter

* `x`: `number` – Der Dividend
* `y`: `number` – Der Divisor

#### Rückgabewert

* `number` – Der Rest der Division (behält das Vorzeichen von `x`)

#### Beispiel

```lua
local remainder = SU.Math.fmod(5.3, 2)    -- liefert 1.3
```
