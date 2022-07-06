# Settlers.SetHealthInArea

## `Settlers.SetHealthInArea(Spieler, Siedlertyp, x, y, Radius, Gesundheit)`

Funktioniert als ein Lazarettbefehl - alle Einheiten vom `Siedlertyp` die unter der angegeben `Gesundheit` sind, werden hochgeheilt.&#x20;

#### Rückgabewert

none

#### Beispiel

```lua
Settlers.SetHealthInArea(1,Settlers.SWORDSMAN_01,100,100,20,120)
```
