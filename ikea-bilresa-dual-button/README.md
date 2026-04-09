# IKEA Bilresa Dual Button - Hybrid Light Control Blueprint

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Fkemoxi%2Fhaos-blueprints%2Fmain%2Fikea-bilresa-dual-button%2Fikea-bilresa-dual-button.yaml)

**Hybrid light control blueprint** for the [IKEA Bilresa Dual Button](https://www.ikea.com/de/de/p/bilresa-fernbedienung-weiss-smart-dualschalter-10604165) remote.

## Functions

- Button 1 single press: Toggle light
- Button 1 hold: Dim brighter
- Button 2 hold: Dim darker
- Button 2 double press: Toggle scenes
  - Warm scene: 40% brightness, 2700K
  - Cool/bright scene: 100% brightness, 4000K

## Installation

### One-click import
[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Fkemoxi%2Fhaos-blueprints%2Fmain%2Fikea-bilresa-dual-button%2Fikea-bilresa-dual-button.yaml)

### Direct raw URL
```text
https://raw.githubusercontent.com/kemoxi/haos-blueprints/main/ikea-bilresa-dual-button/ikea-bilresa-dual-button.yaml
```

### Manual installation
1. Copy the YAML file to:
   `homeassistant/blueprints/automation/kemoxi/ikea-bilresa-dual-button.yaml`
2. In Home Assistant go to:
   `Settings -> Automations & scenes -> Blueprints`
3. Open the menu `⋮` and choose:
   `Reload blueprints`

## Inputs

| Input | Description |
|-------|-------------|
| `light_entity` | Target light |
| `event_btn_1` | Event entity for button 1 |
| `sensor_btn_1` | Hold sensor for button 1 |
| `event_btn_2` | Event entity for button 2 |
| `sensor_btn_2` | Hold sensor for button 2 |

## Requirements

- Home Assistant 2024.1.0 or later
- IKEA Bilresa Dual Button with event entities and matching sensor entities

## Notes

This blueprint uses a hybrid approach:
- Event entities react quickly to button presses
- Sensor entities are used to keep the dimming loop active while holding a button

## License

[MIT License](../LICENSE)
