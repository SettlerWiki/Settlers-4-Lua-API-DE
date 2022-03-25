# unrequest\_event

## `unrequest_event(Funktion, Eventtyp)`

Macht request\_event rückgängig. Hierzu muss der Name der Funktion sowie dessen Eventtyp eingetragen werden. So können Funktionen, die nicht mehr benötigt werden, deaktiviert werden.

#### Rückgabewert

Dnone

#### Beispiel

```lua
unrequest_event(Beispiel, Events.FIVE_TICKS)
```

#### Trivia

Aus komischen Gründen funktioniert unrequest\_event(Funktion,EventTyp) manchmal nicht, wenn die Funktion in der Funktion selbst unrequested wird
