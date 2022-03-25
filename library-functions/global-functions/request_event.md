# request\_event

## `request_event(Funktion, Eventtyp)`

Jede Funktion, die vom Spiel selbst aufgerufen wird, muss hier angefordert werden. Dies wird meist in new\_game() erledigt. Mögliche [Events ](../../api-enums/events.md)sind:

|                                               |                                                                                                  |
| --------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| Events.TICK                                   | Funktion wird jeden Tick aufgerufen                                                              |
| Events.FIVE\_TICKS                            | Funktion wird alle fünf Ticks aufgerufen                                                         |
| Events.VICTORY\_CONDITION\_CHECK              | ähnliche wie FIVE\_TICKS, aber nur, solange das Spiel nicht gewonnen oder verloren wurde         |
| Events.FIRST\_TICK\_OF\_NEW\_OR\_LOADED\_GAME | Beim Starten oder neu laden eines Spiels                                                         |
| Events.FIRST\_TICK\_OF\_NEW\_GAME             | Beim Starten eines neuen Spiels.                                                                 |
| Events.PRODUCTION                             | unbekannt, vermutlich wenn ein Produktionsvorgang beendet wurde.                                 |
| Events.SPACE                                  | unbekannt                                                                                        |
| Events.BUILD\_PRIO                            | unbekannt, vermutlich wenn die Gebäudepriorität geändert wird                                    |
| Events.CREATE\_FOUNDATION\_CART               | unbekannt, vermutlich beim erstellen eines Gründungskarrens.                                     |
| Events.CRUSH\_BUILDING                        | unbekannt, vermutlich wenn ein Gebäude abgerissen wird                                           |
| Events.SHOW\_WORK\_AREA                       | unbekannt, vermutlich wenn der Spieler sich den Arbeitsbereich eines Gebäudes zeigen lässt       |
| Events.MAGIC\_SPELL\_CAST                     | unbekannt, vermutlich wenn ein Spieler einen Zauber nutzt                                        |
| Events.ZOOM\_FACTOR\_CHANGED                  | unbekannt, vermutlich wenn der Spieler den Zoom verstellt                                        |
| Events.WARRIOR\_SENT                          | unbekannt, vermutlich wenn ein Spieler einer Einheit einen Bewegungsbefehl erteilt               |
| Events.WORK\_AREA                             | unbekannt, vermutlich wenn ein Spieler einen Arbeitsbereich neu festlegt                         |
| Events.MENUCLICK                              | unbekannt, vermutlich wenn der Spieler im Menü klickt                                            |
| Events.GOODARRIVE                             | unbekannt, vermutlich wenn ein Siedler eine Ware an ihr Ziel bringt                              |
| Events.WORK\_STATUS                           | unbekannt                                                                                        |
| Events.SETTLER\_CHANGE\_TYPE                  | unbekannt, vermutlich wenn ein Siedler die Rolle wechselt                                        |
| Events.COMMAND                                | unbekannt                                                                                        |
| Events.DRAG\_BUILDING                         | unbekannt, vermutlich wenn der Spieler sich die möglichen Bauplätze für ein Gebäude zeigen lässt |

#### Rückgabewert

none

#### Beispiel

```lua
... Funktion Beispiel und VictoryConditionCheck werden hier geschrieben ...

function new_game()
        request_event(VictoryConditionCheck, Events.VICTORY_CONDITION_CHECK)
        request_event(Beispiel, Events.FIVE_TICKS)
end
function register_functions()
        reg_func(VictoryConditionCheck)
        reg_func(Beispiel)
end
```
