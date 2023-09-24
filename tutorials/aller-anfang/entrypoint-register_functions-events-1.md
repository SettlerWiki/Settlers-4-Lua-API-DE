# Events: register\_functions

Die Function [register\_functions()](../../library-functions/global-functions/register\_functions.md) wird wie [new\_game()](../../library-functions/global-functions/new\_game.md) direkt von S4 selber aufgerufen. Hier definiert ihr, welche Funktionen von euch dem Spiel zur Verfügung gestellt werden für die Verwendung bei Events. Ihr nutzt hierbei die Funktion [reg\_func](../../library-functions/global-functions/reg\_func.md) innerhalb der [register\_functions()](../../library-functions/global-functions/register\_functions.md) um eine Art "Liste" zuschreiben von Funktionen die später in Events aufgerufen werden sollen.



Um eine von auch registrierte Funktion nun auch einem Event zuzuordnen benötigt ihr noch die Funktion [request\_event()](../../library-functions/global-functions/request\_event.md) innerhalb der [new\_game()](../../library-functions/global-functions/new\_game.md). Die häufigsten Events die verwendet werden sind **Events.TICK**, **Events.FIRST\_TICK\_OF\_NEW\_OR\_LOADED\_GAME** und **Events.VICTORY\_CONDITION\_CHECK**

```lua
--setze global eine variable "zahl" mit dem wert 5
zahl = 5

function eineEventFunktion()
    --setze bei globaler variable "zahl" den wert auf 10
    zahl = 10
end

function tickEventFunktion()
   dbg.stm("Hallo, zahl hat den Wert " .. zahl)
end

--bereits behandelt: new_game
function new_game()
    -- später mehr zu request_event
    request_event(eineEventFunktion,Events.FIRST_TICK_OF_NEW_OR_LOADED_GAME)
    request_event(tickEventFunktion,Events.TICK) 
end

function register_functions()
    -- OHNE reg_func(func) WIRD DIE FUNKTION NICHT DURCH EVENTS AUFRUFBAR SEIN
    reg_func(eineEventFunktion)
    reg_func(tickEventFunktion)
end
```

Dieses Codebeispiel hat 2 Events:

* **eineEventFunktion**, welches ein mal am Anfang des Spiels aufgerufen wird (inklusive nach dem Laden) und die variable zahl auf 10 setzt
* **tickEventFunktion**, welche jeden Spieltick (Das Spiel hat \~845Ticks die Minute, entspricht ca. = 14 Ticks pro Sekunde) einen Text ausgibt, welche unter anderem die Variable zahl beinhaltet
