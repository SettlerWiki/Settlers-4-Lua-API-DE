---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Math.atan

## SU.Math.atan(value)

Gibt den Arkustangens (Umkehrfunktion von tan, entspricht `tan^-1`) **in Radiant** zurück ([su.math.rad.md](su.math.rad.md "mention")).

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

* `number` – Winkel im Intervall (-pi/2, pi/2) (in **Radiant**)

#### Beispiel

```lua
local atanValue = SU.Math.atan(1.0)    -- liefert ca. 0.7854 rad (45 Grad)
```
