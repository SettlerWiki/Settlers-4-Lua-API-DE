# register\_functions

## `register_functions()`

Diese Funktion dient zur Registrierung aller Funktionen, die als Event aufgerufen werden. Für Funktionen, die nur von einer anderen Funktion aufgerufen werden, ist dies nicht erforderlich. Diese Funktion wird ähnlich wie new\_game() automatisch beim ersten Tick eines Spiels aufgerufen.

#### Rückgabewert

Da diese Funktion selbst geschrieben wird und vom Spiel intern aufgerufen wird, hat diese Funktion keinen Rückgabewert

#### Beispiel

```lua
... funktionen werden erstellt und mit new_game requested ...

function register_functions()
        reg_func(Beispiel1)
        reg_func(Beispiel2)
        reg_func(Beispiel3)
end
```

