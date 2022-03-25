# Einrichtung & HelloWorld

{% embed url="https://www.youtube.com/watch?v=-n0hyVhtORw" %}
Einstieg isn Scripting von [UltimateSpinDash](https://www.youtube.com/channel/UCXRXmtOKDS3iX2QJDCffwLA)
{% endembed %}

Im ersten Tutorial möchte ich euch zeigen, wie man ein Script überhaupt in eine Map bekommt. Dafür gibt es zwei Möglichkeiten: In der Map selbst oder durch Textdatei im thesettlers4/Script/ Ordner.\
\
Beziehen wir hier auf ein sehr einfachen straight-forward Beispielcode, welcher nur eine Nachricht im Chat ausgibt: "Das Script funktioniert!". Weitere Details zum Code folgen im nächsten Tutorial.

```lua
function new_game()
	dbg.stm("HelloWorld! Das Script funktioniert!")
end
```

## **Script in einer seperaten Datei**

Nehmen wir für dieses Beispiel die Beispiel Editormap "576\_demo.map". **Das Script IN der .map Datei muss dafür leer sein.** Um das Script nun der Map zuweisen zu können müssen wir eine Datei mit dem Namen _"576\_demo.txt"_  im Ordner _".../thesettlers4/Script/ (History Edition)"_ bzw. _".../Die Siedler IV/Script"_ (normale Version) erstellen. In diese Datei fügen wir unseren Scriptcode ein.&#x20;

![](https://web.archive.org/web/20200829133411im\_/https://i.imgur.com/Y9kLOgb.png)

Und das Script sollte dann funktionieren. Ein Beispielbild gibt's hier ganz unten :)

## **Direkt in der Mapdatei hinterlegen**

Sofern du den Script Editor noch nicht hast, kannst du ihn dir entweder zusammen mit [Settlers United ](https://settlers-united.com)holen, oder einzeln auf der [Homepage von MuffinMario](https://s4.muffinmar.io/downloads/) oder auf der [Einführungsseite ](../../)\
\
Sobald du den Installationsschritten gefolgt bist, solltest du beim erneuten Öffnen des S4Editors ein weiteres Fenster bekommen mit einem großen leeren Textfeld, dieses zeigt dir das derzeitge Script der Map an bzw. kannst du das Script der geöffneten Map damit modifizieren.\
\
Zuerst öffnest du die Map, welche du bearbeiten möchtest. Sofern du bereits ein Script am schreiben warst und die geöffnete Map bereits ein Script beinhaltet, wirst du erstmal gefragt, ob du das Script im Script Editor zum Script der derzeitigen Map wechseln möchtest.\
\
Nach dem Öffnen der Map kannst du nun das Beispielscript einfügen, den Button "Script Setzen" drücken und die Map exportieren.

![](https://web.archive.org/web/20200829133411im\_/https://i.imgur.com/MzxcPkC.jpg)

## **Fazit**

Wenn du das gemacht hast und dein Script synaktisch korrekt ist, solltest du jetzt das hier beim Spielstart sehen:

![](https://web.archive.org/web/20200829133411im\_/https://i.imgur.com/9p2ocxC.png)

Man siehe unten wird die Nachricht ausgegeben und das Tutorial ist damit beendet. Beide genannten Möglichkeiten haben ihre Vor- und Nachteile. Um ein Script beispielsweise mit anderen zu teilen, ist es am sinnvollsten dies direkt in der .map Datei zu hinterlegen
