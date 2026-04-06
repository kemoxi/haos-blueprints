# IKEA Bilresa Dual Button - Hybrid Light Control Blueprint

**Hybrid light control blueprint** for the [IKEA Bilresa Dual Button](https://www.ikea.com/de/de/p/bilresa-fernbedienung-weiss-smart-dualschalter-10604165).

### Functions

- Button 1 single press: Toggle light
- Button 1 hold: Dim brighter  
- Button 2 hold: Dim darker
- Button 2 double press: Toggle scenes (warm 40%/2700K ↔ cool 100%/4000K)

## 🚀 Installation

[![Import Blueprint](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Fkemoxi%2Fhaos-blueprints%2Fmain%2Fikea-bilresa-dual-button%2Fikea-bilresa-dual-button.yaml)

**Direct URL:**  
`https://raw.githubusercontent.com/kemoxi/haos-blueprints/main/ikea-bilresa-dual-button/ikea-bilresa-dual-button.yaml`

**Manual:** Copy YAML to `config/blueprints/automation/kemoxi/ikea-bilresa-dual-button.yaml` → Reload blueprints.

## Inputs

| Input | Description |
|-------|-------------|
| `light_entity` | Target light entity |
| `event_btn_1` | Button 1 event entity |
| `sensor_btn_1` | Button 1 hold sensor |
| `event_btn_2` | Button 2 event entity |
| `sensor_btn_2` | Button 2 hold sensor |

## License

[MIT License](LICENSE)
