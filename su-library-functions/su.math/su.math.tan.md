---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Math.tan

## SU.Math.tan(angle)

Gibt den Tangens eines Winkels (**in Radiant** [su.math.rad.md](su.math.rad.md "mention")

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

* `number` – Tangenswert im Bereich (-unendlich, unendlich)

#### Beispiel

```lua
local tanValue = SU.Math.tan(0.7854)    -- liefert ca. 1.0 (Tangens von 45 Grad)
```
