---
description: 'SU Library: ab Version 0.7.0'
---

# SU.GameData

{% hint style="info" %}
Die Felder die es hier gibt sind die Parameter der Prototypen, **verändern daher in den allermeisten Fällen nur die Werte von NEUEN Einheiten**. Bekannte **Ausnahmen** sind Geschwindigkeiten, Lebenspunkte (die fungieren als Maximal-Lebenspunkte, d.h. bereits existierende Einheiten können hochgeheilt werden).
{% endhint %}

{% hint style="info" %}
Bekannte **Probleme**, die behoben werden:

* Settler.Speed: ändert nichts (von SU überschrieben)
{% endhint %}

<details>

<summary>Building fields</summary>

| `SU.GameData.BUILDING_FIELD_IHOTSPOTX`            | Bild-Ankerpunkt            |
| ------------------------------------------------- | -------------------------- |
| `SU.GameData.BUILDING_FIELD_IHOTSPOTY`            | Bild-Ankerpunkt            |
| `SU.GameData.BUILDING_FIELD_STONE`                | Kosten: Steine             |
| `SU.GameData.BUILDING_FIELD_BOARDS`               | Kosten: Bretter            |
| `SU.GameData.BUILDING_FIELD_GOLD`                 | Kosten: Gold               |
| `SU.GameData.BUILDING_FIELD_LINES`                |                            |
| `SU.GameData.BUILDING_FIELD_ISWATERBUILDING`      |                            |
| `SU.GameData.BUILDING_FIELD_BUILDERNUMBER`        |                            |
| `SU.GameData.BUILDING_FIELD_BUILDERINFO`          |                            |
| `SU.GameData.BUILDING_FIELD_FLAG_XOFFSET`         |                            |
| `SU.GameData.BUILDING_FIELD_FLAG_YOFFSET`         |                            |
| `SU.GameData.BUILDING_FIELD_DOOR_XOFFSET`         |                            |
| `SU.GameData.BUILDING_FIELD_DOOR_YOFFSET`         |                            |
| `SU.GameData.BUILDING_FIELD_WORKINGPOS_XOFFSET`   |                            |
| `SU.GameData.BUILDING_FIELD_WORKINGPOS_YOFFSET`   |                            |
| `SU.GameData.BUILDING_FIELD_MINIFLAG_XOFFSET`     |                            |
| `SU.GameData.BUILDING_FIELD_MINIFLAG_YOFFSET`     |                            |
| `SU.GameData.BUILDING_FIELD_BITBOUNDINGRECT_MINX` |                            |
| `SU.GameData.BUILDING_FIELD_BITBOUNDINGRECT_MAXX` |                            |
| `SU.GameData.BUILDING_FIELD_BITBOUNDINGRECT_MINY` |                            |
| `SU.GameData.BUILDING_FIELD_BITBOUNDINGRECT_MAXY` |                            |
| `SU.GameData.BUILDING_FIELD_BUILDINGRADIUS`       |                            |
| `SU.GameData.BUILDING_FIELD_PILENUMBER`           |                            |
| `SU.GameData.BUILDING_FIELD_PILES`                |                            |
| `SU.GameData.BUILDING_FIELD_SETTLERNUMBER`        |                            |
| `SU.GameData.BUILDING_FIELD_SETTLERBOTTOMCOUNT`   |                            |
| `SU.GameData.BUILDING_FIELD_SETTLERTOPCOUNT`      |                            |
| `SU.GameData.BUILDING_FIELD_FIRSTTOPSETTLERIDX`   |                            |
| `SU.GameData.BUILDING_FIELD_SETTLERS`             |                            |
| `SU.GameData.BUILDING_FIELD_PATCHSETTLERSLOT`     |                            |
| `SU.GameData.BUILDING_FIELD_INHABITANT`           |                            |
| `SU.GameData.BUILDING_FIELD_TOOL`                 |                            |
| `SU.GameData.BUILDING_FIELD_PRODUCTIONDELAY`      |                            |
| `SU.GameData.BUILDING_FIELD_SEARCHTYPE`           |                            |
| `SU.GameData.BUILDING_FIELD_KIND`                 |                            |
| `SU.GameData.BUILDING_FIELD_INFLUENCERADIUS`      |                            |
| `SU.GameData.BUILDING_FIELD_EXPLORERRADIUS`       | Sichtweite des Gebäudes    |
| `SU.GameData.BUILDING_FIELD_WORKINGAREARADIUS`    | Größe des Arbeitebereiches |
| `SU.GameData.BUILDING_FIELD_DUMMYVALUE`           |                            |
| `SU.GameData.BUILDING_FIELD_HITPOINTS`            | Lebenspunkte               |
| `SU.GameData.BUILDING_FIELD_ARMOR`                | Rüstungswert               |
| `SU.GameData.BUILDING_FIELD_PATCHES`              |                            |
| `SU.GameData.BUILDING_FIELD_TRIGGERS`             |                            |

</details>

<details>

<summary>Object fields</summary>

| `SU.GameData.OBJECT_FIELD_UNKNOWN1`                      |   |
| -------------------------------------------------------- | - |
| `SU.GameData.OBJECT_FIELD_TOTALBLOCKINGRINGS`            |   |
| `SU.GameData.OBJECT_FIELD_REPELLINGRINGS`                |   |
| `SU.GameData.OBJECT_FIELD_TOTALBLOCKINGORREPELLINGRINGS` |   |
| `SU.GameData.OBJECT_FIELD_TOTALRINGS`                    |   |
| `SU.GameData.OBJECT_FIELD_UNKNOWN5`                      |   |
| `SU.GameData.OBJECT_FIELD_UNKNOWN6`                      |   |
| `SU.GameData.OBJECT_FIELD_HASPINGPONG`                   |   |

</details>

<details>

<summary>Settler fields</summary>

| `SU.GameData.SETTLER_FIELD_ROLE`    |                                                                                   |
| ----------------------------------- | --------------------------------------------------------------------------------- |
| `SU.GameData.SETTLER_FIELD_SPEED`   | Geschwindigkeit in Ticks/Feld (kleiner = schneller)                               |
| `SU.GameData.SETTLER_FIELD_HEALTH`  | Lebenspunkte (gleichzeitig Maximal-Lebenspunkte für bereits existierende Siedler) |
| `SU.GameData.SETTLER_FIELD_DAMAGE`  | Schaden, der verursacht wird (ohne Kampfkraft-Skalierung)                         |
| `SU.GameData.SETTLER_FIELD_ARMOR`   | Rüstungswert                                                                      |
| `SU.GameData.SETTLER_FIELD_TOOL`    | benötigtes Werkzeug                                                               |
| `SU.GameData.SETTLER_FIELD_OTHER`   |                                                                                   |
| `SU.GameData.SETTLER_FIELD_MISC`    | z.B. bei Heilern wie viel sie heilen (ohne Kampfkraft-Skalierung)                 |
| `SU.GameData.SETTLER_FIELD_DAMAGE2` |                                                                                   |
| `SU.GameData.SETTLER_FIELD_DAMAGE3` |                                                                                   |

</details>

<details>

<summary>Vehicle fields</summary>

| `SU.GameData.VEHICLE_FIELD_BOARDS`           | Kosten Bretter                                                                              |
| -------------------------------------------- | ------------------------------------------------------------------------------------------- |
| `SU.GameData.VEHICLE_FIELD_IRONBARS`         | Kosten Eisen                                                                                |
| `SU.GameData.VEHICLE_FIELD_WALKSTEPS`        | Geschwindigkeit in Ticks/Feld (kleiner = schneller)                                         |
| `SU.GameData.VEHICLE_FIELD_HITPOINTS`        | Lebenspunkte (gleichzeitig Maximal-Lebenspunkte für bereits existierende Fahrzeuge/Schiffe) |
| `SU.GameData.VEHICLE_FIELD_ARMOR`            | Rüstungswert                                                                                |
| `SU.GameData.VEHICLE_FIELD_DAMAGE`           | Schaden, der verursacht wird (ohne Kampfkraft-Skalierung)                                   |
| `SU.GameData.VEHICLE_FIELD_READYTOFIREDELAY` | Intervall, in dem gefeuert wird                                                             |
| `SU.GameData.VEHICLE_FIELD_MAXAMMO`          | maximale Munition                                                                           |

</details>
