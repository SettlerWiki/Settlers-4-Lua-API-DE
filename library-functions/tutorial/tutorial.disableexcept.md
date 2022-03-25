# Tutorial.DisableExcept

## `Tutorial.DisableExcept([control, ...])`

Schaltet alle Knöpfe aus, so dass man z.B. nicht mehr die Gebäude in der Gebäudeauswahl auswählen kann, oder Soldaten in der Kaserne erstellen kann. Alle Parameter sind Knöpfe die nicht davon betroffen sind. Es gibt ca. 1700 Controls, die hier nicht alle passen aufzulisten. Stattdessen gehen Sie bitte auf Controls->Numbers

#### Rückgabewert

none

#### Beispiel

```lua
-- Schaltet alle Controls ab
Tutorial.DisableExcept()
-- Schaltet alle Controls ab, außer die vier Knöpfe unter der Minimap (Gebäude, Siedler, Produktioneinstellungen, Statistiken)
Tutorial.DisableExcept
(
        Control.DLG_MINIMAP_CMD_BUILD,
        Control.DLG_MINIMAP_CMD_FIGURES,
        Control.DLG_MINIMAP_CMD_PRODUCTION,
        Control.DLG_MINIMAP_CMD_STATISTICS     
)
```
