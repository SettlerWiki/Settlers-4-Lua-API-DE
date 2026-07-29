---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Math.max

## SU.Math.max(x, ...)

Gibt den größten Wert aus den übergebenen Argumenten zurück.

#### Parameter

* `x`: `number` – Das erste, zwingend erforderliche Argument
* `...`: `number` _(optional)_ – Weitere durch Komma getrennte Zahlen

#### Rückgabewert

* `number` – Der höchste numerische Wert unter den Argumenten
* `nil`: Falls kein Argument übergeben wird

#### Beispiel

```lua
local maxValue = SU.Math.max(3, 12, -5, 8)    -- liefert 12
```
