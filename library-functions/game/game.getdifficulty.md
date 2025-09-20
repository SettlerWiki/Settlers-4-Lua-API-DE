# Game.GetDifficulty

## `Game.GetDifficulty()`

Prüft, welche Schwierigkeit eingestellt ist.

#### ACHTUNG: prüft nur LOKAL, welche Schwierigkeit eingestellt ist ⇒ haben Spieler im S4-Menü unterschiedliche Einstellungen, gibt es einen Desync!

#### Rückgabewert

0 für leicht, 1 für normal

#### Beispiel

```lua
local localDifficulty = Game.GetDifficulty()
```
