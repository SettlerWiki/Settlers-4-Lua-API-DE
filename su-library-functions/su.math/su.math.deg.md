---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Math.deg

## SU.Math.deg(angleRad)

Wandelt einen Winkel von Radiant (rad) in Grad (Degree) um.

{% hint style="info" %}
Winkelfunktionen arbeiten mit **Gleitkomma**zahlen, daher sollte das **End**resultat meist **gerundet werden**! **Zwischen**resultate können und sollen meist **so bleiben** wie sie sind. **Beispiel:**

```lua
local degrees = SU.Math.deg(3.14159)    -- liefert 179.9999...
local roundedDegrees = SU.Math.round(degrees)    -- liefert 180
```
{% endhint %}

#### Parameter

* `angleRad`: `number` – Winkel in Radiant (rad)

#### Rückgabewert

* `number` – Winkel in Grad (0 bis 360 Grad)

#### Beispiel

```lua
local degrees = SU.Math.deg(3.14159)    -- liefert ca. 180.0
```
