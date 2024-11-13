# AI.SetPlayerVar

## `AI.SetPlayerVar(Partei, PlayerVar, Parameter1, Parameter2, Parameter3)`

Legt bestimmte Werte für die KI fest, einige funktionieren auch für menschliche Spieler. Werte können zum Teil getrennt für die Schwierigkeitsstufen (Parameter1 bis Parameter3) des Spiels festgelegt werden (Leicht, Normal und eine ungenutzte schwere Schwierigkeit), andere haben nur einen Parameter. Mögliche PlayerVars:

<table><thead><tr><th width="358.4697289556449"></th><th>DESC</th></tr></thead><tbody><tr><td>AttackMode</td><td>0 für passiv, 1 für defensiv (reagiert extrem auf Provokation), 2 für Standard, 3 für Aggressiv</td></tr><tr><td>AttackDelay</td><td>Zeit in Minuten, die vergehen muss, bevor die Partei angreifen kann</td></tr><tr><td>AttackChancePartial</td><td></td></tr><tr><td>AttackThresholdPartial</td><td></td></tr><tr><td>AttackThresholdTotal</td><td></td></tr><tr><td>SoldierLimitAbsolute</td><td></td></tr><tr><td>SoldierLimitRelative</td><td></td></tr><tr><td>WarmachineMode</td><td></td></tr><tr><td>MagicMode</td><td></td></tr><tr><td>SpellMask</td><td></td></tr><tr><td>SpellFlags</td><td></td></tr><tr><td>DTManaPerSphere</td><td>bestimmt, wie viel Mana das Dunkle Volk pro Kugel bekommt. Standardmäßig 6, funktioniert auch für spielbare Dunkle Völker</td></tr><tr><td>DTMaxFarmsBase</td><td></td></tr><tr><td>DTMaxFarmsPerHour</td><td>begrenzt die Anzahl der Pilzfarmen, die das Dunkle Volk pro Stunden bauen kann</td></tr><tr><td>DTExtraManaBaseAmount</td><td></td></tr><tr><td>DTExtraManaAmountPerFarm2</td><td>ja das ist ne 2 wtf is this</td></tr><tr><td>DTExtraManaDelay</td><td></td></tr><tr><td>DTExtraManaLimit</td><td></td></tr><tr><td>UsePioneers</td><td></td></tr><tr><td>DTManakopterHallDelay</td><td></td></tr><tr><td>DTManakopterDelay</td><td></td></tr><tr><td>DTManakopterLimit</td><td></td></tr><tr><td>DTManakopterLimit</td><td></td></tr></tbody></table>

Einheiten reagieren nur auf Befehle, wenn bei ihrer Erstellung der Parameter "zum Squad hinzufügen" auf 1 gestellt ist, z.B. bei Schiffen Sonst kann es passieren, dass die Einheiten erscheinen, aber nichts tun.

#### Rückgabewert

none

#### Beispiel

```lua
AI.SetPlayerVar(2, "AttackMode", 2,3,3)
AI.SetPlayerVar(1, "DTManaPerSphere", 8)
AI.SetPlayerVar(2, "DTMaxFarmsPerHour", 2, 5, 10)
AI.SetPlayerVar(2, "AttackDelay", 500, 50, 10)
AI.SetPlayerVar(2, "SoldierLimitAbsolute", 50,100,300)
AI.SetPlayerVar(2, "SoldierLimitRelative", 50,50,150)
```

