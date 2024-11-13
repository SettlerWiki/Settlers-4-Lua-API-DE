# Buildings.AddBuilding

## `Buildings.AddBuilding(x, y, Spieler, Gebäude)`

Platziert ein Gebäude für den genannten Spieler an den angegebenen Koordinaten.

**Achtung:** durch **fehlerhaftes Verhalten** wird das Gebäude platziert, auch wenn die Stelle eigentlich blockiert ist. Eine Lösung wird momentan in `UBO Test` getestet.

**Achtung:** zusätzlich **stürzt das Spiel ab**, wenn sich an dieser Stelle bereits Siedler befinden, da diese dadurch danach bewegungsunfähig sind.\
**⇒ Diese Funktion sollte nur am Anfang im Script stehen**, wo noch keine Siedler und Warenstapel existieren / platziert wurden und später nicht mehr verwendet werden!

#### Rückgabewert

Eindeutige Gebäude-ID

#### Beispiel

```lua
Buildings.AddBuilding(100,100, 1, Buildings.GUARDTOWERSMALL)
```
