---
description: 'SU Library: ab Version 0.7.0'
---

# SU.Math.cosh

## SU.Math.cosh(value)

Gibt den Kosinus Hyperbolicus einer Zahl zurück.

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

* `number` – Ergebnis im Intervall \[1, unendlich)

#### Beispiel

```lua
local coshValue = SU.Math.cosh(0)    -- liefert 1.0
```
