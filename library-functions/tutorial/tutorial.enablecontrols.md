# Tutorial.EnableControls

## `Tutorial.EnableControls([control, ...])`

Schaltet die ausgewählten Controls wieder ein

#### Rückgabewert

none

#### Beispiel

```lua
-- schaltet die Knöpfe "Freie Siedler"/"Spezialisten" Auswählen und "Spezialisten" Erhöhen wieder an
Tutorial.EnableControls(
        Control.BTN_SPECIALIST_UP,
        Control.BTN_SETTLERS,
        Control.BTN_SETTLERS_SPECIALISTS,
        Control.BTN_SPECIALIST1
)
-- Funktion die nichts anstellt, somit gar nichts macht.
Tutorial.EnableControls()
```

