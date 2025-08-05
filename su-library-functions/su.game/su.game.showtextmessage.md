---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Game.ShowTextMessage

## SU.Game.ShowTextMessage(msg\[, icon=8\[, lifetime\_s=120\[, x, y]]]

Zeigt die Nachricht im Chat an.

**Kurzform** siehe[su.game.stm.md](su.game.stm.md "mention").

#### Parameter

* `icon`: bestimmt das Symbol links neben der Nachricht im Chat (siehe Tabelle)

<table><thead><tr><th width="161">icon (optional)</th><th>Symbol links neben der Nachricht im Chat</th></tr></thead><tbody><tr><td>0</td><td>rot</td></tr><tr><td>1</td><td>blau</td></tr><tr><td>2</td><td>grün</td></tr><tr><td>3</td><td>gelb</td></tr><tr><td>4</td><td>violett</td></tr><tr><td>5</td><td>orange</td></tr><tr><td>6</td><td>türkis</td></tr><tr><td>7</td><td>weiß</td></tr><tr><td>8 (Standard)</td><td>Rufzeichen</td></tr></tbody></table>

* `lifetime_s` (optional): Zeit in Echtzeit-Sekunden (nicht Spielzeit!), wie lange die Nachricht sichtbar sein soll. Danach verschwindet sie von alleine. \
  `lifetime_s=-1` bewirkt, dass die **Nachricht** (selbst beim Klick darauf) **nicht verschwindet!**\
  &#xNAN;**`lifetime_s=-2`** ist die am längsten bestehende aber wegklickbare Nachricht.
* `x, y` (optional): Koordinaten, zu denen der Bildschirm springt, wenn auf die Nachricht gedrückt wird.

#### Beispiel

```lua
SU.Game.ShowTextMessage("Hey there!")
SU.Game.stm("Hey there!")    // Kurzform (stm = ShowTextMessage)
SU.Game.ShowTextMessage("Hey there!", 1, 20)    // blaues icon, 20 Sekunden
SU.Game.ShowTextMessage("Hey there!", 8, 120, 100, 50)    // Bildschirm springt zu (100,50)
SU.Game.ShowTextMessage("Hey there!", 8, -1, 100, 50)    // Nachricht bleibt für immer bestehen
```
