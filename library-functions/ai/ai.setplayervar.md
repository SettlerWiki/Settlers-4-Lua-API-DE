# AI.SetPlayerVar

## `AI.SetPlayerVar(Partei, PlayerVar, Parameter1, Parameter2, Parameter3)`

Legt bestimmte Werte für die KI fest, einige funktionieren auch für menschliche Spieler. Werte können zum Teil getrennt für die Schwierigkeitsstufen (Parameter1 bis Parameter3) des Spiels festgelegt werden (Leicht, Normal und eine ungenutzte schwere Schwierigkeit), andere haben nur einen Parameter. Mögliche PlayerVars:

|                           | DESC                                                                                                                      |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| AttackMode                | 0 für passiv, 1 für defensiv (reagiert extrem auf Provokation), 2 für Standard, 3 für Aggressiv                           |
| AttackDelay               | Zeit in Minuten, die vergehen muss, bevor die Partei angreifen kann                                                       |
| AttackChancePartial       |                                                                                                                           |
| AttackThresholdPartial    |                                                                                                                           |
| AttackThresholdTotal      |                                                                                                                           |
| SoldierLimitAbsolute      |                                                                                                                           |
| SoldierLimitRelative      |                                                                                                                           |
| WarmachineMode            |                                                                                                                           |
| MagicMode                 |                                                                                                                           |
| SpellMask                 |                                                                                                                           |
| SpellFlags                |                                                                                                                           |
| DTManaPerSphere           | bestimmt, wie viel Mana das Dunkle Volk pro Kugel bekommt. Standardmäßig 6, funktioniert auch für spielbare Dunkle Völker |
| DTMaxFarmsBase            |                                                                                                                           |
| DTMaxFarmsPerHour         | begrenzt die Anzahl der Pilzfarmen, die das Dunkle Volk pro Stunden bauen kann                                            |
| DTExtraManaBaseAmount     |                                                                                                                           |
| DTExtraManaAmountPerFarm2 | ja das ist ne 2 wtf is this                                                                                               |
| DTExtraManaDelay          |                                                                                                                           |
| DTExtraManaLimit          |                                                                                                                           |
| UsePioneers               |                                                                                                                           |
| DTManakopterHallDelay     |                                                                                                                           |
| DTManakopterDelay         |                                                                                                                           |
| DTManakopterLimit         |                                                                                                                           |
| DTManakopterLimit         |                                                                                                                           |

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

