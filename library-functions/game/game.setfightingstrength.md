# Game.SetFightingStrength

## `Game.SetFightingStrength(playerID, value)`

Setzt die o**ffensive** **Kampfkraft** des Spielers auf den angegebenen Wert (maximal 150). Wenn der Wert für einen Spieler einmal per Script festgelegt wurde, skaliert er nicht mehr normal mit dem Siedlungswert. Das kann aber mit **-1 zurückgesetzt** werden.

#### Parameter

* `playerID [1-8]`: Spieler-ID, **Index 0 ist ungültig!**
* `value [-1, 0-150]`: offensive Kampfkraft, -1 löscht den gesetzten Wert und das Spiel berechnet die Kampfkraft wieder wie gehabt

#### Rückgabewert

none

#### Beispiel

```lua
Game.SetFightingStrength(1, 150)    ; Kampfkraft von Spieler 1 auf 150%
Game.SetFightingStrength(1, -1)     ; Skalierung zurückgesetzt
```
