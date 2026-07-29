---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Math.acosh

## SU.Math.acosh(value)

Gibt den Areakosinus Hyperbolicus (Umkehrfunktion von `cosh` [su.math.cosh.md](su.math.cosh.md "mention"), entspricht `cosh`<sup>`-1`</sup>) zurück.

{% hint style="info" %}
Winkelfunktionen arbeiten mit **Gleitkomma**zahlen, daher sollte das **End**resultat meist **gerundet werden**! **Zwischen**resultate können und sollen meist **so bleiben** wie sie sind. **Beispiel:**

```lua
local degrees = SU.Math.deg(3.14159)    -- liefert 179.9999...
local roundedDegrees = SU.Math.round(degrees)    -- liefert 180
```
{% endhint %}

#### Parameter

* `value`: `number` – Gleitkommazahl im Intervall \[1, unendlich)

#### Rückgabewert

* `number` – Ergebnis im Intervall \[0, unendlich)
* `nan` (not a number, [su.math.isnan.md](su.math.isnan.md "mention")): Fehler bei Eingaben kleiner als 1

#### Beispiel

```lua
local acoshValue = SU.Math.acosh(2.5)    -- liefert ca. 1.567
```
