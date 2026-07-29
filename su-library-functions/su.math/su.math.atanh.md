---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Math.atanh

## SU.Math.atanh(value)

Gibt den Areatangens Hyperbolicus (Umkehrfunktion von `tanh` [su.math.tanh.md](su.math.tanh.md "mention"), entspricht `tanh`<sup>`-1`</sup>) zurück.

{% hint style="info" %}
Winkelfunktionen arbeiten mit **Gleitkomma**zahlen, daher sollte das **End**resultat meist **gerundet werden**! **Zwischen**resultate können und sollen meist **so bleiben** wie sie sind. **Beispiel:**

```lua
local degrees = SU.Math.deg(3.14159)    -- liefert 179.9999...
local roundedDegrees = SU.Math.round(degrees)    -- liefert 180
```
{% endhint %}

#### Parameter

* `value`: `number` – Gleitkommazahl im offenen Intervall (-1, 1)

#### Rückgabewert

* `number` – Das Ergebnis im Bereich (-unendlich, unendlich)
* `nan` (not a number, [su.math.isnan.md](su.math.isnan.md "mention")): Fehler bei Wertebereichen außerhalb von (-1, 1)
* `inf` oder `-inf` ([su.math.isinf.md](su.math.isinf.md "mention")): Bei genau 1 oder -1

#### Beispiel

```lua
local atanhValue = SU.Math.atanh(0.5)    -- liefert ca. 0.5493
```
