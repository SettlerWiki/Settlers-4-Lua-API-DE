---
description: 'SU Library: erst ab Version 0.6.1 verfügbar!'
---

# SU.Game.SetFightingStrengthBaseValuePerNumberOfPlayers

## SU.Game.SetFightingStrengthBaseValuePerNumberOfPlayers(numberOfPlayers)

Setzt den **Basiswert** der Kampfkraftberechnung entsprechend der angegebenen Anzahl an Spielern.\
Die **Kampfkraftberechnung** an sich bleibt aber **unverändert**.

⇒ Damit kann z.B. der **Einfluss von Zuschauern** auf die Kampfkraft **vermieden** werden.

#### Notiz

* Diese Methode funktioniert erst **nach der Initialisierung der Karte** (⇒ `Events.FIRST_TICK_OF_NEW_GAME`), **nicht** in `new_game`!

#### Parameter

* `numberOfPlayers [-1, 1-8]`: Anzahl der Spieler, die einen Einfluss auf den Basiswert haben sollen, -1 stellt den Standardwert wieder her.

#### Beispiel

```lua
SU.Game.SetFightingStrengthBaseValuePerNumberOfPlayers(2) ; als gäbe es nur 2 Spieler
```

Vollständiges Beispiel:

```lua
function initGame()
    SU.Game.SetFightingStrengthBaseValuePerNumberOfPlayers(2)
end

function new_game()
    request_event(initGame, Events.FIRST_TICK_OF_NEW_GAME)
end

function register_functions()
    reg_func(initGame)
end
```
