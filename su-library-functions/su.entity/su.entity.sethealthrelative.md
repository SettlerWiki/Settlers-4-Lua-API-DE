---
description: 'SU Library: erst ab Version 0.6.0 verfügbar!'
---

# SU.Entity.SetHealthRelative

## SU.Entity.SetHealthRelative(entityId, relativeHealth)

Setzt die relativen Lebenspunkte der angegebenen Entität.

#### Notiz

* Haben Entitäten keine Lebenspunkte (=0), werden sie ignoriert
* Der gegebene Relativwert (`relativeHealth`) wird auf \[0, 100] beschränkt
* `relativeHealth=0` setzt die Lebenspunkte zwar auf 0, löst aber **nicht** die Kill-Funktion aus (Entität ist danach quasi 1-Hit)
* `relativeHealth` im negativen Bereich (<0) wird ignoriert und die Funktion nicht ausgeführt (siehe Rückgabewert)

#### Parameter

* `entityId`: ID der Entität
* `relativeHitpoints`: neue relativen Lebenspunkte (siehe Notizen)

#### Rückgabewert

* Neue (**absoluten!**) Lebenspunkte
* -1: sonst / Fehler

#### Beispiel

<pre class="language-lua"><code class="lang-lua">local newHealth = SU.Entity.SetHealthRelative(entityID, relativeHitpoints)
<strong>
</strong><strong>local newHealth = SU.Entity.SetHealthRelative(1, 90)
</strong>-- Setzt EntityId 1 auf 90% Leben
dbg.stm(newHealth) -- neuer Lebenswert (absolut)
</code></pre>
