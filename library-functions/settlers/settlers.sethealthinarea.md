# Settlers.SetHealthInArea

## `Settlers.SetHealthInArea(Spieler, Siedlertyp, x, y, Radius, UnderOrExactlyHealth)`

Funktioniert als ein Lazarettbefehl - alle Einheiten vom `Siedlertyp` die unter der angegeben `UnderOrExactlyHealth` sind, werden geheilt.

#### Notiz

* Diese Funktion **setzt nicht** dem Namen entsprechend die **Lebenspunkte**, **sondern heilt!**\
  **⇒** [su.settlers.sethealthinarea.md](../../su-library-functions/su.settlers/su.settlers.sethealthinarea.md "mention") ([su.entity.sethealth.md](../../su-library-functions/su.entity/su.entity.sethealth.md "mention"), [su.entity.sethealthrelative.md](../../su-library-functions/su.entity/su.entity.sethealthrelative.md "mention"))

#### Rückgabewert

none

#### Beispiel

```lua
Settlers.SetHealthInArea(1,Settlers.SWORDSMAN_01,100,100,20,120)
```
