---
description: 'SU Library: erst ab Version 0.6.0 verfügbar!'
---

# SU.Entity.SetHealth

## SU.Entity.SetHealth(entityId, newHealth)

Setzt die Lebenspunkte der angegebenen Entität.

#### Notiz

* Haben Entitäten keine Lebenspunkte (=0), werden sie ignoriert
* Der gegebene Absolutwert (`newHealth`) wird auf die maximalen Lebenspunkte der Entität beschränkt
* `newHealth=0` setzt die Lebenspunkte zwar auf 0, löst aber **nicht** die Kill-Funktion aus (Entität ist danach quasi 1-Hit)
* `newHealth` im negativen Bereich (<0) wird ignoriert und die Funktion nicht ausgeführt (siehe Rückgabewert)

#### Parameter

* `entityId`: ID der Entität
* `newHealth`: neue absoluten Lebenspunkte (siehe Notizen)

#### Rückgabewert

* Neue Lebenspunkte
* -1: sonst / Fehler

#### Beispiel

<pre class="language-lua"><code class="lang-lua">local newHealth = SU.Entity.SetHealth(entityID, health)

local newHealth = SU.Entity.SetHealth(1, 100)
-- Setzt EntityId 1 auf 100 Leben
<strong>dbg.stm(newHealth) -- Neuer Lebenswert
</strong>
</code></pre>
