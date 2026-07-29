---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Math.cos

## SU.Math.cos(angle)

Gibt den Kosinus eines Winkels (**in Radiant** [su.math.rad.md](su.math.rad.md "mention")) zurück.

{% hint style="info" %}
Winkelfunktionen arbeiten mit **Gleitkomma**zahlen, daher sollte das **End**resultat meist **gerundet werden**! **Zwischen**resultate können und sollen meist **so bleiben** wie sie sind. **Beispiel:**

```lua
local degrees = SU.Math.deg(3.14159)    -- liefert 179.9999...
local roundedDegrees = SU.Math.round(degrees)    -- liefert 180
```
{% endhint %}

#### Parameter

* `angle`: `number` – Winkel in **Radiant** (rad)

#### Rückgabewert

* `number` – Kosinuswert im Intervall \[-1, 1]

#### Beispiel

```lua
local cosValue = SU.Math.cos(3.14159)    -- liefert ca. -1.0
```
