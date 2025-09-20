# Externe Lua Skripte

Skripte können direkt über den Editor in der Karte (**.map**-Datei) abgespeichert werden, haben dann jedoch eine **Zeichenlimitierung** von ca. **65.000 Zeichen**. Für wen das zu wenig ist:

**⇒** Externe Lua Skripts, die **umgehen** diese **Zeichenlimitierung**.



## Verwendung

#### ACHTUNG: jede/r Spieler/in muss das Skript manuell in den entsprechenden Ordner kopieren!



#### Gleicher Name, Script-Ordner - kein Problem

Das Spiel sucht automatisch bei Spielstart im Installationsordner von S4 unter `.\Script` nach einer **.txt**-Datei mit genau **demselben Namen wie die Karte** und lädt dieses Skript.\
Z.B. `C:\Program Files (x86)\Ubisoft\Ubisoft Game Launcher\games\thesettlers4\Script`.



#### Unterordner

Soll ein Skript aus einem expliziten **Unterordner** von `.\Script` wie z.B. `.\Script\User` verwendet werden, muss

```lua
$User\$
```

im Editor **als Karten-Skript** gesetzt werden, wobei "User" bereits **relativ zu ".\Script"** ist, auch mehrere Verschachtelungen sind möglich (`.\Script\User\sub1\sub2` etc.).



#### Skript-Name ≠ Karten-Name

Bei dem SU-Balancing-Modus **UBO-Test** können auch explizit Skripte geladen werden, indem direkt die **.txt**-Datei angegeben wird. Z.B. lädt

```lua
$User\myScript.txt$
```

als Karten-Skript direkt das Skript "myScript.txt" aus dem Ordner `.\thesettlers4\Script\User`,  egal wie die Karte heißt - praktisch für allgemeine Skripte.





#### Notizen

* $-Zeichen nicht vergessen!
* **Lua-Skripte** müssen die **Endung ".txt"** haben, **nicht** "~~.lua~~"!
* **Umlaute** werden nur richtig als Textnachricht im Chat ausgegeben (dbg.stm(), etc.), wenn die **.txt-Datei** als **"ISO 8859-1" kodiert** ist, siehe [https://php-de.github.io/jumpto/utf-8/](https://php-de.github.io/jumpto/utf-8/) (in Notepad++ einzustellen unter "Codierung > Weitere Codepages > Westeuropäisch > ISO 8859-1").
