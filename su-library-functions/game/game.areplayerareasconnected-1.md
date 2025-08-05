---
description: 'SU Library: erst ab Version 0.5.0 verfügbar!'
---

# SU.Game.BlockToweringOverAxis

## SU.Game.BlockToweringOverAxis(enable\[, axis=SU.Axis.NONE])

Wenn aktiviert, können **neu gebaute** Türme kein Land mehr über die angegebene Achse einnehmen (**ausgehend von der Startposition des Spielers!**).

Eroberte Türme nehmen weiterhin überall Land ein.

#### Parameter

* `enable [0,1]`: de- (0) / aktiviert (1) die Funktionalität
* `axis` (optional): Achse [ai-1.md](../../su-api-enums/ai-1.md "mention")

#### Beispiel

```lua
SU.Game.BlockToweringOverAxis(1, SU.Axis.LONG)
```
