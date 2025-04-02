# SU.Game.SetBeds

## SU.checkVersion(version)

Setzt vom angegebenen Spieler die Anzahl an Betten, **die auch ohne Wohnhäuser bestehen bleiben. Betten von Wohnhäusern bleiben weiterhin zusätzlich bestehen.**

#### Parameter

* `version`: Version, die mindestens vorhanden sein muss

#### Beispiel

```lua
SU.Game.SetBeds(1, 100)    // Spieler 1 hat nun 100 Betten (exkl. Wohnhäusern)
```
