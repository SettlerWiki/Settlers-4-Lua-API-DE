# Lokale vs Netzwerk-Funktionen

Das Lua-Skript und auch das Spiel an sich wird im Multiplayer auf allen PCs synchron ausgeführt. Das hat zur Folge, dass alles zeitgleich passiert und es keine Desyncs gibt. Desync bedeutet, dass der Spielstatus zwischen Spielern variiert und es daher nicht mehr sinnvoll fertiggespielt werden kann, weil beispielsweise die KI auf unterschiedlichen PCs unterschiedliche Aktionen ausführt.

Benutzereingaben müssen aber immer über das Netzwerk ausgetauscht werden, damit alles synchron bleibt.

Um die Anzahl der Netzwerk-Events zu reduzieren, läuft ansonsten alles lokal bei jedem Spieler deterministisch ab (das bedeutet in diesem Fall zufällig aber trotzdem vorhersehbar - es stehen zu Beginn des Spiels bereits alle zukünftigen Zufallszahlen fest, nur als Mensch weiß man das noch nicht).

#### Lokale Funktionen (fast alle!)

Damit das Lua-Skript ebenfalls synchron läuft, müssen natürlich auch hier alle ausgeführten Funktionen in derselben Reihenfolge mit demselben Ergebnis ablaufen. Um abermals das Netzwerk vor redundenter Information zu entlasten, werden **die allermeisten Lua-Funktionen lokal ausgeführt**.\
Dies hat zur Folge, dass wenn solche Funktionen nicht exakt gleich ausgeführt werden, es **direkt zu einem Desync kommt!**

#### Netzwerk-Funktionen (in der Unter-Überschrift gekennzeichnet)

Natürlich gibt es auch Ausnahmen, wo selbst Lua-Funktionen auf die Eingabe von Anwendern reagieren muss. Dafür gibt es spezielle Netzwerk-Funktionen, die zwar nur bei einem Spieler lokal ausgeführt werden müssen, dann aber im Endeffekt trotzdem bei allen synchron ausgeführt werden, da die Ausführung über das Netzwerk synchronisiert wird.

Solche Funktionen sind als **Netzwerk-Funktionen** auf den entsprechenden Dokumentations-Seiten **in der Unter-Überschrift gekennzeichnet**.
