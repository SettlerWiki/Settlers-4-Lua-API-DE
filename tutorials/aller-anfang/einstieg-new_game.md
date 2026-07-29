# Einstieg: new\_game

Die[ new\_game()](../../library-functions/global-functions/new_game.md) Funktion ist der Haupteinstiegspunkt jedes Mapscripts. Neben [register\_functions()](../../library-functions/global-functions/register_functions.md) ist dies die einzige Methode, welche vom S4 Spiel selbst direkt aufgerufen wird. (Hier wird der globale Bereich mal abgesehen, da der immer ausgeführt wird)\
\
**Beispiel: Was wird ausgeführt?**

```lua
function new_game()
    dbg.stm("Ja, new_game wird vom Spiel aufgerufen")
end
function register_functions()
    dbg.stm("Ja, register_functions wird vom Spiel aufgerufen")
end

function eineAndereFunktion()
    dbg.stm("Nein, andere Funktionen werden vom Spiel nicht aufgerufen")
end

function noch_eine_andere_funktion()
    dbg.stm("Nein, andere Funktionen werden vom Spiel nicht aufgerufen")
end

dbg.stm("Ja, der globale Bereich wird vom Spiel aufgerufen!") -- nicht schön!!!
```

Beim Spielstart sieht die Konsole möglicherweise so aus\
<img src="https://web.archive.org/web/20200829133418im_/https://i.imgur.com/dUluw2S.png" alt="" data-size="original">\
Nach dem Laden des Spielstandes:\
<img src="https://web.archive.org/web/20200829133418im_/https://i.imgur.com/8G8gZ5n.png" alt="" data-size="original"><br>

## **Funktionskriterien**

\
In Lua ist es relativ egal, wie man eine Funktion nennt, das Hauptkriterium ist, dass der Name nicht mit einer Zahl anfängt und keine ä,ö,ü,ß Umlaute enthält.&#x20;

```lua
function 2Fähler() 
   -- Das ganze Skript wird nicht Funktionieren und Siedler IV gibt keine Fehlermeldung aus!
end
```

Aber **bei Einstiegspunkten muss der Name übereinstimmen**, da das Spiel nur diese Funktionen aufruft.

## **Fazit**

Wie ihr seht ist der globale Bereich nicht sehr gut zum Skripte schreiben, weshalb das Modularisieren mit Funktionen immer die bessere Alternative ist.
