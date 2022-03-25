# dbg.sg

## `dbg.sg(x, y, radius, groundID)`

Setzt den Boden auf koordinate x,y im Umkreis von radius Einheiten auf groundID. \
radius = 0 ist nichts \
groundID kann ein Wert zwischen 0-255 sein. \
Es empfiehlt sich meine klitzekleine "Library" [https://github.com/MuffinMario/Siedler-IV-Lua-Ground-Library/blob/master/groundlibrary.lua](https://github.com/MuffinMario/Siedler-IV-Lua-Ground-Library/blob/master/groundlibrary.lua) zu benutzen um sich Zeit zu sparen.

#### Rückgabewert

none

#### Beispiel

```lua
dbg.sg(400,200,5,18) -- Setze alle Böden um 400/200 im Umkreis von 5 Einheiten auf den Boden "Grasinsel"



-- mit der Library!!
--Angenommen überall ist um 100/100 im Umkreis von +6 Einheiten ist Wasser Level 1:
Grounds.SetGround(100,100,5,Grounds.SAND) -- Sand um das Wasser im Umkreis von 5
-- zwischen sand und gras gibt es keine übergangsböden (normalerweise 1-2)
Grounds.SetGround(100,100,4,Grounds.GRASS) -- Gras im Umkreis von 4 (Alle Böden waren davor Sand)
```

#### Trivia

Die Funktion greift sehr tief in die Spielengine ein. Setzt man z.b. Gras auf Wasser werden trotzdem Wassertiere erscheinen. Die Funktion ist nicht so gütig, wie der Editor. Platzierst du z.B. Gras im Radius=1 auf ein Schlammfeld, gibt es keinen Übergang zwischen Gras und Schlamm. Allgemein ist diese Funktion NICHT für konventionelle Maps geeignet.\
Es hat sehr komische Eigenschaften, welche ich auf dem in der Beschreibung genannten GitHub-Link alle dokumentiert habe.
