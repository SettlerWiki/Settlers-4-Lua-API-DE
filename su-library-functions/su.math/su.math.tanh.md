---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Math.tanh

## SU.Math.tanh(value)

Gibt den Tangens Hyperbolicus einer Zahl zurück.

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

* `number` – Das Ergebnis im Intervall (-1, 1)

#### Beispiel

```lua
local tanhValue = SU.Math.tanh(1)    -- liefert ca. 0.7616
```
