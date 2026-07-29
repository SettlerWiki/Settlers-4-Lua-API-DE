---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Math.asinh

## SU.Math.asinh(value)

Gibt den Areasinus Hyperbolicus (Umkehrfunktion von `sinh` [su.math.sinh.md](su.math.sinh.md "mention"), entspricht `sinh`<sup>`-1`</sup>) zurück.

{% hint style="info" %}
Winkelfunktionen arbeiten mit **Gleitkomma**zahlen, daher sollte das **End**resultat meist **gerundet werden**! **Zwischen**resultate können und sollen meist **so bleiben** wie sie sind. **Beispiel:**

```lua
local degrees = SU.Math.deg(3.14159)    -- liefert 179.9999...
local roundedDegrees = SU.Math.round(degrees)    -- liefert 180
```
{% endhint %}

#### Parameter

* `value`: `number` – Beliebige reelle Zahl

#### Rückgabewert

* `number` – Das Ergebnis im Bereich (-unendlich, unendlich)

#### Beispiel

```lua
local asinhValue = SU.Math.asinh(1.0)    -- liefert ca. 0.881
```
