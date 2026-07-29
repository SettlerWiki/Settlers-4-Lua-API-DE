---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Math.rad

## SU.Math.rad(angleDeg)

Wandelt einen Winkel **von Grad** (Degree) in Radiant (rad) um.

{% hint style="info" %}
Winkelfunktionen arbeiten mit **Gleitkomma**zahlen, daher sollte das **End**resultat meist **gerundet werden**! **Zwischen**resultate können und sollen meist **so bleiben** wie sie sind. **Beispiel:**

```lua
local degrees = SU.Math.deg(3.14159)    -- liefert 179.9999...
local roundedDegrees = SU.Math.round(degrees)    -- liefert 180
```
{% endhint %}

#### Parameter

* `angleDeg`: `number` – Winkel in **Grad**

#### Rückgabewert

* `number` – Winkel in **Radiant** (rad)

#### Beispiel

```lua
local radians = SU.Math.rad(180)    -- liefert ca. 3.14159 rad
```
