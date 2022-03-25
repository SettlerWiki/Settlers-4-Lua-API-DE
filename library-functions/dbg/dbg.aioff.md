# dbg.aioff

## `dbg.aioff(id)`

Komplementär zu [dbg.aion(id)](dbg.aion.md).

#### Rückgabewert

none

#### Beispiel

```lua
-- angenommen menschlicher spieler partei = 1:
dbg.aioff(3) -- deaktiviert Partei 3 - eine AI
dbg.aion(3) -- aktiviert Partei 3 AI wieder

dbg.aion(1) -- "Spiel Verloren" + AI spielt für dich mit allen normalen Verhaltensweisen
dbg.aion(1) -- deaktiviert die AI beim Spieler wieder. "Spiel Verloren" bleibt dennoch stehen

dbg.aion(0) -- anscheinend gar nichts. selbst 0 zu setzen, nachdem man 1 hatte, ändert nichts.
```

#### Trivia

Die Funktion wird in Tutorial09 und Tutorial10 benutzt, um die AIs zu deaktivieren.
