# Die Vars.Save Variablen

Für **unbeschränkt viele Variablen** über Speicherstände hinweg **siehe** [suvars.md](../su-library/suvars.md "mention").



Nun da wir gelernt haben wo wir mit dem Scripten anfangen, nehmen wir uns mal ein kleines, aber interessantes Thema vor: Die Speichervariablen.\
\
Damit eine große Scriptmap die sich aktiv am Spielgeschehen der Map beteiligt richtig funktioniert, muss sie sich logischerweise nicht nur zu Start eines Spiels gut funktionieren, sondern auch nach dem laden eines Spielstandes. \
\
Leider ist in der Speicherdatei eines Spielstandes nicht alles gespeichert, was im globalen Bereich definiert wurde. Beim laden eines Spielstandes wird daher alles im Script zurückgesetzt wie beim ersten Start des Spieles.\
Das bedeutet für uns im Klartext: Alle Variablen welche durch das Spiel geändert wurden, werden beim erneuten Spielstand laden zurückgesetzt bzw. nicht erneut erstellt. \
Natürlich haben die Entwickler sich da was ausgedacht. Die **Vars.SaveX** Variablen. Diese sind 9 Variablen (Vars.Save1 bis Vars.Save9) die alle **Zahlen abspeichern** können.

Ein konkretes Beispiel zu dem Verhalten von normalen Variablen und Vars.SaveX Variablen sollte das veranschaulichen:

{% hint style="info" %}
_Info: Die Funktion_ [_register\_functions_](../../library-functions/global-functions/register_functions.md) _bzw_[ _request\_event_ ](../../library-functions/global-functions/request_event.md)_gehört fürs erste ignoriert. Alles was man wissen muss ist: **varSaveStandard** wird nur beim allerersten Start des Spiels aufgerufen und **onGameStartSave** bei sowohl neuem Spiel als auch geladenen. **tostring(x)** lässt uns bei nicht nummer/text einen text zurückbekommen (hier nil)_
{% endhint %}

```lua
GlobaleKonstante = 100
NichtKonstant = 150

function varSaveStandard()
    NichtInGlobal = 20
    -- ändern der globalen Variable NichtKonstant
    NichtKonstant = 200
    Vars.Save1 = 1
    Vars.Save2 = "Zwei"
    Vars.Save9 = 9
    Vars.Save10 = 10
end
function onGameStartSave()
    dbg.stm("GlobaleKonstante : " .. GlobaleKonstante)
    dbg.stm("NichtInVars : " .. tostring(NichtInGlobal))
    dbg.stm("NichtKonstant : " .. tostring(NichtKonstant))
    dbg.stm("Vars.Save1: " .. Vars.Save1)
    dbg.stm("Vars.Save2: " .. Vars.Save2)
    dbg.stm("Vars.Save9: " .. Vars.Save9)
    dbg.stm("Vars.Save10: " .. tostring(Vars.Save10))
end
function new_game()
    varSaveStandard()
    request_event(onGameStartSave,Events.FIRST_TICK_OF_NEW_OR_LOADED_GAME)
end

function register_functions()
    reg_func(onGameStartSave)
end
```

## Beim Spielbeginn

![](https://web.archive.org/web/20200829133422im_/https://i.imgur.com/tBCXU1P.png)

![](https://web.archive.org/web/20200829133422im_/https://i.imgur.com/oR3Q6b6.png)

## **Beim Spiel laden**

![](https://web.archive.org/web/20200829133422im_/https://i.imgur.com/BM6AcAP.png)

![](https://web.archive.org/web/20200829133422im_/https://i.imgur.com/1YhQzpV.png)

Hier haben wir 5 Typen von Variablen:

* Konstante, global initiierte Variablen (GlobaleKonstante)
* Variable, global initiierte Variablen (NichtKonstant)
* Konstante, lokal initiierte Variablen (NichtInGlobal)
* Speichervariable mit Zahl (Vars.Save1 und 9)
* Inkorrekte Speichervariable (Vars.Save2 und 10)

Hier kann man einiges feststellen, was sich nach dem Laden ändert:\
**NichtInVars** wird nach dem Laden nie auf einen Wert gesetzt und ist deshalb nil (not initialized (zu deutsch: nicht initialisiert)).\
**NichtInGlobal** (ups! **NichtInVars** ist ein Schreibfehler :) ) ändert sich ja im Laufe des Spiels, in einer Funktion. Stell dir nun vor du würdest nun einen Minutencounter haben, der sagt, ab welcher Minute die Gegner Soldaten bekommen und angreifen. Der wäre nun wieder auf dem Standardwert und das Script wäre verbuggt.\
Hier sieht man auch gut, dass Vars.Save nur Zahlen und auch nur Vars.Save1 bis Vars.Save9 speichert; Vars.Save2 und Vars.Save10 sind beide wieder auf unerwartete Werte gestoßen.

## **Fazit**

Benötigst du eine Variable über einen gewissen Zeitraum und die Variable verändert ihren Wert, dann solltest du die Variable lieber auf Vars.SaveX tun. Aber aufgepasst, da du nur 9 mögliche Speichervariablen hast!

## **Tipp**

Da Lua alle Variablen global erreichbar macht, solange man nicht local davorsetzt ([Lua 3.2 Manual](https://www.lua.org/manual/3.2/manual.html#localvar)), lohnt es sich zu fragen: Muss diese Variable global sein? Im Bezug auf Siedler IV ist das aber meistens irrelevant und wird nur zum Problem, wenn man Fehler macht und einen Variablennamen mehrmals benutzt

```lua
function baum()
   x = 100
   y = 100
   Map.AddDecoObject(x,y, 1)
end
function stein()
   c = 200 -- UPS! VERTIPPT!! Das sollte x sein!
   y = 200
   Map.AddDecoObject(x,y, 124)
end
```

**Szenario 1:** baum() und dann stein() aufrufen: Der Stein wird auf 100|200 platziert (blöd, denn es sollte 200|200 sein)\
**Szenario 2:** stein() aufrufen: Die Funktion bricht ab, weil es die Variable x nicht gibt. (bessere Option, aber trotzdem blöd)

```lua
function baum()
   local x = 100
   local y = 100
   Map.AddDecoObject(x,y, 1)
end
function stein()
   local c = 200 -- UPS! VERTIPPT!! Das sollte x sein!
   local y = 200
   Map.AddDecoObject(x,y, 124)
enda
```

So kann man Szenario 1 vermeiden. Ist die Funktion baum() zu Ende, wird auch x und y wieder gelöscht.

Das war natürlich nur ein sehr primitives Beispiel und meistens ist es schwerer so etwas zu beheben, weshalb man immer ein gewissen "Stil" behalten sollte, damit man sowas im weiten Rahmen vermeiden kann. Aber das war's dann auch dazu.
