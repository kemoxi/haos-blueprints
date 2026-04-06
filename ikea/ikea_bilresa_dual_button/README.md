# IKEA Bilresa Dual Button

Home Assistant automation blueprint for the IKEA Bilresa Dual Button remote.

## Features

- Button 1 single press: Toggle light
- Button 1 hold: Dim brighter
- Button 2 hold: Dim darker
- Button 2 double press: Toggle between two scenes
  - Warm scene: 40% brightness, 2700K
  - Cool/bright scene: 100% brightness, 4000K
- Hybrid dimming logic using event entities plus sensor-state checks
- Small debounce delay for smoother behavior

## Blueprint file

```text
ikea_bilresa_light_control.yaml
```

## Import into Home Assistant

Home Assistant supports blueprint imports from GitHub URLs. To import a blueprint, open:

`Settings -> Automations & scenes -> Blueprints -> Import Blueprint` [web:3]

Use the raw GitHub URL of the YAML file:

```text
https://raw.githubusercontent.com/kemoxi/homeassistant/main/ikea/ikea_bilresa_dual_button/ikea_bilresa_light_control.yaml
```

## Required inputs

- `light_entity`  
  The target light entity.

- `event_btn_1`  
  Event entity for button 1.

- `sensor_btn_1`  
  Sensor entity used to detect the hold state for button 1.

- `event_btn_2`  
  Event entity for button 2.

- `sensor_btn_2`  
  Sensor entity used to detect the hold state for button 2.

## Button mapping

| Control | Action |
|---------|--------|
| Button 1 single press | Toggle light |
| Button 1 hold | Dim brighter |
| Button 2 hold | Dim darker |
| Button 2 double press | Toggle warm scene / cool-bright scene |

## How it works

This blueprint uses a hybrid approach:
- The event entities detect the actual button actions.
- The sensor entities are checked in the dimming repeat loop.
- This allows smooth hold-to-dim behavior while still reacting quickly to button presses.

## Notes

- The warm scene uses 40% brightness at 2700K.
- The cool/bright scene uses 100% brightness at 4000K.
- The double-press action on button 2 switches between these two scenes based on the current color temperature.
- `mode: single` and a short delay help reduce overlapping executions.

## License

MIT
