# dbg.aion

## `dbg.aion(id)`

Eine Funktion die in normalen Maps nicht korrekt funktioniert. Abgesehen wurde sie wahrscheinlich exklusiv für Tutorials.

Für normale Maps gilt: \
dbg.aion(0) hat keinen sichtbaren Effekt \
dbg.aion(z) z gleich Menschliche Partei: zeigt dem Spieler ein "Spiel Verloren" Banner an (man kann jedoch spielen) und eine KI spielt mit dem Spieler. \
dbg.aion(z) z gleich AI Partei: Aktiviert die AI sofern sie deaktiviert war.

INFO: Was im Multiplayer passiert, wenn man einen anderen Spieler auf aion/aioff setzt ist unbekannt. Hypothese ist: Desynchronisation.

#### Rückgabewert

none

#### Beispiel

```lua
-- angenommen menschlicher spieler partei = 1:
dbg.aioff(3) -- deaktiviert Partei 3 - eine AI
dbg.aion(3) -- aktiviert Partei 3 AI wieder

dbg.aion(1) -- "Spiel Verloren" + AI spielt für dich mit allen normalen Verhaltensweisen

dbg.aion(0) -- anscheinend gar nichts. selbst 0 zu setzen, nachdem man 1 hatte, ändert nichts.
```

#### Trivia

Die Funktion wird in allen Maps nur ein mal in Tutorial08 mit dem Aufruf dbg.aion(0) benutzt. Dort werden alle AIs deaktiviert, um die Soldaten nicht zu ihrem Turm laufen zu lassen. (Unbestätigt!, es kann sich auch um ein Übrigbleibsel handeln, und die AIs sind in Tutorials standardmäßig verschieden zu den normalen Maps) (Tutorialexklusive Eigenschaft / Funktioniert nicht mit eigenen Maps)
