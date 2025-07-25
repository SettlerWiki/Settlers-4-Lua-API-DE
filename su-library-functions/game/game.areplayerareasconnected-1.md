---
description: 'SU Library: erst ab Version 0.4.0 verfügbar!'
---

# SU.Game.BlockToweringOverAxis

## SU.Game.BlockToweringOverAxis(enable\[, axis=SU.Axis.NONE])

Wenn aktiviert, können Türme kein Land mehr über die angegebene Achse einnehmen (**ausgehend von der Startposition des Spielers!**).

#### Notiz:

* Werden Türme auf der anderen Seite der Achse eingenommen, während diese Funktion aktiv ist, nehmen die Türme kein Land ein und zerstören keine umliegenden Gebäude. Oft werden die einzunehmenden Türme auch direkt zerstört statt eingenommen.

#### Parameter

* `enable [0,1]`: de- (0) / aktiviert (1) die Funktionalität
* `axis` (optional): Achse [ai-1.md](../../su-api-enums/ai-1.md "mention")

#### Beispiel

```lua
SU.Game.BlockToweringOverAxis(1, SU.Axis.LONG)
```
