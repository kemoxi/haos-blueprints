# HAOS Blueprints

Focused Home Assistant automations. Simple setup, clear controls.

## Blueprints

| Blueprint | What it does | Install |
| --- | --- | --- |
| [IKEA Bilresa Dual Button](ikea-bilresa-dual-button/) | Toggle a light, hold to dim, and switch between two color-temperature presets. | [![Import blueprint](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Fkemoxi%2Fhaos-blueprints%2Fmain%2Fikea-bilresa-dual-button%2Fikea-bilresa-dual-button.yaml) |
| [Water Alarm](water-alarm/) | Send water-leak notifications, repeat alerts while the sensor is wet, and optionally turn off a switch. | [![Import blueprint](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Fkemoxi%2Fhaos-blueprints%2Fmain%2Fwater-alarm%2Fcritical-water-leak-alarm.yaml) |

Open a blueprint's page for its requirements, inputs and behavior before importing.

## Installation

### Quick Install

Choose an import button above, open your Home Assistant instance, and confirm the import. Then create an automation from the imported blueprint and configure its inputs.

### Manual Install

Each blueprint page provides its direct YAML URL. Paste that URL into the blueprint import dialog in Home Assistant.

Alternatively, copy the YAML file into a personal subfolder of your Home Assistant configuration directory:

```text
<config>/blueprints/automation/kemoxi/
```

`<config>` means your Home Assistant configuration directory, not a literal folder name to create. If a manually copied blueprint does not appear, reload automations and check the Blueprints page again.

## Repository layout

```text
haos-blueprints/
├── ikea-bilresa-dual-button/
│   ├── README.md
│   └── ikea-bilresa-dual-button.yaml
├── water-alarm/
│   ├── README.md
│   └── critical-water-leak-alarm.yaml
├── .gitignore
├── LICENSE
└── README.md
```

Each blueprint has its own folder, documentation and importable YAML file.

## Feedback

When reporting an issue, include the blueprint name, Home Assistant version, relevant integration, expected behavior and what actually happened. Remove credentials and personal information from traces or screenshots before sharing them.

## License

[MIT](LICENSE) · Copyright 2026 kemoxi
