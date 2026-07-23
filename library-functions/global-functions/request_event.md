# request\_event

## `request_event(Funktion, Eventtyp)`

Jede Funktion, die vom Spiel selbst aufgerufen wird, muss hier angefordert werden. Dies wird meist in new\_game() erledigt. Mögliche [Events ](../../api-enums/events.md)sind die folgenden. Die Parameter geben an, welche Parameter die Funktion dann vom Spiel aus bekommt.

| Event                                         | Beschreibung                                                                            | Parameter                                                                                                                                    |
| --------------------------------------------- | --------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| Events.TICK                                   | Funktion wird jeden Tick aufgerufen                                                     | none                                                                                                                                         |
| Events.FIVE\_TICKS                            | Funktion wird alle fünf Ticks aufgerufen                                                | none                                                                                                                                         |
| Events.VICTORY\_CONDITION\_CHECK              | ähnlich wie FIVE\_TICKS, aber nur, solange das Spiel nicht gewonnen oder verloren wurde | none                                                                                                                                         |
| Events.FIRST\_TICK\_OF\_NEW\_OR\_LOADED\_GAME | <p>Beim Starten oder neu laden eines Spiels<br>(nach Events.FIRST_TICK_OF_NEW_GAME)</p> | none                                                                                                                                         |
| Events.FIRST\_TICK\_OF\_NEW\_GAME             | Beim Starten eines neuen Spiels.                                                        | none                                                                                                                                         |
| Events.MAGIC\_SPELL\_CAST                     | Wenn ein Spieler einen Zauber nutzt                                                     | playerID, spellID, x, y                                                                                                                      |
| Events.SETTLER\_CHANGE\_TYPE                  | Wenn ein Siedler die Rolle wechselt                                                     | **new** settlerType ( [settlers.md](../../api-enums/settlers.md "mention") )                                                                 |
| Events.GOODARRIVE                             | Wenn ein Siedler eine Ware an ihr Ziel bringt                                           | buildingType ( [buildings.md](../../api-enums/buildings.md "mention") ), goodType ( [goods.md](../../api-enums/goods.md "mention") ), amount |
| ====================                          | ALLE WEITEREN FUNKTIONIEREN NUR IM TUTORIAL                                             | ====================                                                                                                                         |
| Events.PRODUCTION                             | Wenn ein Produktionsvorgang beendet wurde                                               | goodType ( [goods.md](../../api-enums/goods.md "mention") )                                                                                  |
| Events.SPACE                                  | Wenn die Leertaste gedrückt wurde                                                       | none                                                                                                                                         |
| Events.BUILD\_PRIO                            | Wenn die Gebäudepriorität geändert wird                                                 |                                                                                                                                              |
| Events.CREATE\_FOUNDATION\_CART               | Wenn ein Gründungskarren fertiggestellt wurde                                           |                                                                                                                                              |
| Events.CRUSH\_BUILDING                        | Wenn ein Gebäude abgerissen wurde                                                       |                                                                                                                                              |
| Events.SHOW\_WORK\_AREA                       | Wenn der Spieler sich den Arbeitsbereich eines Gebäudes zeigen lässt                    |                                                                                                                                              |
| Events.ZOOM\_FACTOR\_CHANGED                  | Wenn der Spieler den Zoom verstellt                                                     | none                                                                                                                                         |
| Events.WARRIOR\_SENT                          | Wenn ein Spieler einer Einheit einen Bewegungsbefehl erteilt                            | none?                                                                                                                                        |
| Events.WORK\_AREA                             | Wenn ein Spieler einen Arbeitsbereich neu festlegt                                      |                                                                                                                                              |
| Events.MENUCLICK                              | Wenn der Spieler im Menü klickt                                                         |                                                                                                                                              |
| Events.WORK\_STATUS                           | unbekannt                                                                               |                                                                                                                                              |
| Events.COMMAND                                | unbekannt                                                                               | command ( [dialog.md](../../api-enums/dialog.md "mention") )                                                                                 |
| Events.DRAG\_BUILDING                         | Wenn der Spieler sich die möglichen Bauplätze für ein Gebäude zeigen lässt              | buildingType ( [buildings.md](../../api-enums/buildings.md "mention") )                                                                      |

#### Rückgabewert

none

#### Beispiel

```lua
... Funktion Beispiel und VictoryConditionCheck werden hier geschrieben ...

function new_game()
        request_event(VictoryConditionCheck, Events.VICTORY_CONDITION_CHECK)
        request_event(Beispiel, Events.FIVE_TICKS)
        request_event(onSpellCast, Events.MAGIC_SPELL_CAST)
end
function register_functions()
        reg_func(VictoryConditionCheck)
        reg_func(Beispiel)
        reg_func(onSpellCast)
end

function onSpellCast(playerID, spellID, x, y)
    dbg.stm("Events.MAGIC_SPELL_CAST: " .. tostring(playerID) .. ", " .. tostring(spellID) .. ", " .. tostring(x) .. ", " .. tostring(y))
end
```
