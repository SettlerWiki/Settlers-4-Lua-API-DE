---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Math.asin

## SU.Math.asin(value)

Gibt den Arkussinus (Umkehrfunktion von `sin` [su.math.sin.md](su.math.sin.md "mention"), entspricht `sin`<sup>`-1`</sup>) **in Radiant** zurück ([su.math.rad.md](su.math.rad.md "mention")).

{% hint style="info" %}
Winkelfunktionen arbeiten mit **Gleitkomma**zahlen, daher sollte das **End**resultat meist **gerundet werden**! **Zwischen**resultate können und sollen meist **so bleiben** wie sie sind. **Beispiel:**

```lua
local degrees = SU.Math.deg(3.14159)    -- liefert 179.9999...
local roundedDegrees = SU.Math.round(degrees)    -- liefert 180
```
{% endhint %}

#### Parameter

* `value`: `number` – Gleitkommazahl im Intervall \[-1, 1]

#### Rückgabewert

* `number` – Winkel im Intervall \[-pi/2, pi/2] (in **Radiant**)
* `nan` (not a number, [su.math.isnan.md](su.math.isnan.md "mention")): Fehler bei Eingaben außerhalb von \[-1, 1]

#### Beispiel

```lua
local asinValue = SU.Math.asin(0.5)    -- liefert ca. 0.5236 rad (30 Grad)
```
