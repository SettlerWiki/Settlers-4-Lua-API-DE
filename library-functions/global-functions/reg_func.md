# reg\_func

## `reg_func(function)`

Registriert eine Funktion, die vom Spiel als Event aufgerufen werden soll. Für Funktionen, die nur von einer anderen Funktion aufgerufen werden, ist dies nicht erforderlich. Reg\_func wird in der zweiten Einstiegsfunktion register\_functions implementiert.

#### Rückgabewert

Diese Funktion gibt keinen Wert zurück.

#### Beispiel

```lua
--== Diese Funktion muss registriert werden, da sie beim allerersten Tick eines Spieles durch ein Event aufgerufen wird
function InitVar()
        -- setze die erste Speichervariable auf 0
        Vars.Save1 = 0
end
--== Diese Funktion muss nicht registriert werden, da sie nicht als Event aufgetragen wird
function print(text)
        dbg.stm(text) -- gibt text im Chatfenster zurück
end
-- Das Spiel ruft new_game von selber auf
function new_game()
        -- InitVar wird ein mal beim allerersten Tick eines Spieles aufgerufen
        request_event(InitVar, Events.FIRST_TICK_OF_NEW_GAME)
end

-- Das Spiel ruft register_functions von selber auf
function register_functions()
        -- registriere Funktion als "Eventfunktion"
        reg_func(InitVar)
end
```

