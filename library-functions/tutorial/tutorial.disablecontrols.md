# Tutorial.DisableControls

## `Tutorial.DisableControls([control, ...])`

Das Gegenstück zu Tutorial.DisableExcept. Schaltet alle Controls aus, die in den Parametern stehen

#### Rückgabewert

none

#### Beispiel

```lua
-- schaltet die Knöpfe "Freie Siedler"/"Spezialisten" Auswählen und "Spezialisten" Erhöhen aus
Tutorial.DisableControls(
        Control.BTN_SPECIALIST_UP,
        Control.BTN_SETTLERS,
        Control.BTN_SETTLERS_SPECIALISTS,
        Control.BTN_SPECIALIST1
)
-- Funktion die nichts ausstellt, somit gar nichts macht.
Tutorial.DisableControls()
```
