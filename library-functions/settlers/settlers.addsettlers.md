# Settlers.AddSettlers

## `Settlers.AddSettlers(x, y, Spieler, Siedlertyp, Menge)`

Erzeugt Siedler an den angegebenen Koordinaten.

#### Rückgabewert

none

#### Beispiel

```lua
Settlers.AddSettlers(403, 378, 1, Settlers.SQUADLEADER, 1) --//Ein Hauptmann für Spieler 1 bei den Koordinaten 403/378
Settlers.AddSettlers(100, 300, 1, Settlers.SLAVED_SETTLER, 25)  --//25 versklavte Siedler (können nicht im Editor platziert werden) für Spieler 1 bei den Koordinaten 100/300
```
