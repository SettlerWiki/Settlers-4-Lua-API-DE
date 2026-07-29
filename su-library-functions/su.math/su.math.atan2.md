---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Math.atan2

## SU.Math.atan2(y, x)

Gibt den Arkustangens der zwei Variablen y und x im Radiant-Maß zurück. Berücksichtigt automatisch das Vorzeichen beider Argumente zur Bestimmung des Quadranten.

{% hint style="info" %}
Winkelfunktionen arbeiten mit **Gleitkomma**zahlen, daher sollte das **End**resultat meist **gerundet werden**! **Zwischen**resultate können und sollen meist **so bleiben** wie sie sind. **Beispiel:**

```lua
local degrees = SU.Math.deg(3.14159)    -- liefert 179.9999...
local roundedDegrees = SU.Math.round(degrees)    -- liefert 180
```
{% endhint %}

#### Parameter

* `y`: `number` – y-Koordinate (Ordinate)
* `x`: `number` – x-Koordinate (Abszisse)

#### Rückgabewert

* `number` – Winkel im Intervall (-pi, pi] (in **Radiant** [su.math.rad.md](su.math.rad.md "mention"))

#### Beispiel

```lua
local angle = SU.Math.atan2(1.0, -1.0)    -- liefert ca. 2.3562 rad (135 Grad)
```
