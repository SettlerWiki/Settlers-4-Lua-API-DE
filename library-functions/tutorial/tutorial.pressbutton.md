# Tutorial.PressButton

## `Tutorial.PressButton(dialog, control)`

Drückt den Knopf #control im derzeitigen **dialog**

#### Rückgabewert

none

#### Beispiel

```lua
-- drückt den Gebäudeknopf unter der Minimap
Tutorial.PressButton(Dialog.DLG_MINIMAP, Control.DLG_MINIMAP_CMD_BUILD)
-- Drückt den "Grundgebäude" Knopf im Untermenü der Gebäudeauswahl (Grundgebäude = Holzfällter, Steinmetz, etc.=)
Tutorial.PressButton(Dialog.DLG_BUILDSUBMENU, Control.DLG_BUILDSUBMENU_CMD_BASIC)
```

