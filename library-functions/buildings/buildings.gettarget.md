# Buildings.GetTarget

## `Buildings.GetTarget(gebäudeID)`

Gibt das Ziel des Gebäudes zurück. Marktplätze und Häfen können diese Funktion nutzen.

#### Rückgabewert

DDie GebäudeID des Ziels

#### Beispiel

```lua
-- Bekomme die ID des ersten Marktplatzes von Partei 1
buildingID = Buildings.GetFirstBuilding(1,Buildings.MARKETPLACE)
-- Bekomme die ID des Zielpunktes
targetID = Buildings.GetTarget(buildingID)
-- wenn die ID ungleich 0 (kein Ziel) ist, schreibe Text in das Chatfenster
if targetID ~= 0 then
        dbg.stm("Marktplatz hat ein Ziel ausgewählt")
end

```
