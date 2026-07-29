---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Math.min

## SU.Math.min(x, ...)

Gibt den kleinsten Wert aus den übergebenen Argumenten zurück.

#### Parameter

* `x`: `number` – Das erste, zwingend erforderliche Argument
* `...`: `number` _(optional)_ – Weitere durch Komma getrennte Zahlen

#### Rückgabewert

* `number` – Der niedrigste numerische Wert unter den Argumenten
* `nil`: Falls kein Argument übergeben wird

#### Beispiel

```lua
local minValue = SU.Math.min(3, 12, -5, 8)    -- liefert -5
```
