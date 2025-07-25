---
description: 'SU Library: erst ab Version 0.2.0 verfügbar!'
---

# SU.Map.SetResource

## SU.Map.SetResource(x, y, resource)

Setzt an den angegebenen Koordinaten die Ressource.

#### Notiz

* **Diese Funktion sollte nur am Berg und im Wasser verwendet werden!**
* Diese Funktion ermöglicht es aber, **jegliche Ressource auf jeglichem Untergrund zu setzen, was aber kaum jemals Sinn ergibt**, z.B. Fisch auf Land - auch wenn der Fischer dort nicht angeln wird - deswegen sollte vorher der Untergrund auf den entsprechend richtigen Typ geprüft werden! (⇒ [settlers.addsettlers-6.md](settlers.addsettlers-6.md "mention"))
* Die beiden Ressourcen **Stein** ("SU.Resources.STONE\_X") und **Holz** ("SU.Resources.WOOD") **können nicht gesetzt werden / machen keinen Sinn und können das Spielverhalten zerstören!**

#### Parameter

* `x, y`: Koordinaten
* `resource`: [ai-9.md](../../su-api-enums/ai-9.md "mention")

#### Rückgabewert

* 1: erfolgreich gesetzt
* 0: sonst / Fehler

#### Beispiel

```lua
local success = SU.Map.SetResource(x, y, SU.Resources.COAL_15)
```
