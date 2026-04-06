# Home Assistant Blueprints by kemoxI

This repository contains personal Home Assistant blueprints and related documentation.

## Structure

```text
.
├── .gitignore
├── LICENSE
├── README.md
└── ikea/
    └── ikea_bilresa_dual_button/
        ├── README.md
        └── ikea_bilresa_light_control.yaml
```

## Included Blueprint

### IKEA Bilresa Dual Button

Path:  
`ikea/ikea_bilresa_dual_button/ikea_bilresa_light_control.yaml`

Functions:
- Button 1 single press: Toggle light
- Button 1 hold: Dim brighter
- Button 2 hold: Dim darker
- Button 2 double press: Toggle between warm and cool-bright scene

## Import into Home Assistant

Home Assistant can import blueprints from GitHub by URL.

Use the raw GitHub URL of the YAML file in:

`Settings -> Automations & scenes -> Blueprints -> Import Blueprint`

After upload to GitHub, the raw URL will look like:

```text
https://raw.githubusercontent.com/kemoxI/homeassistant/main/ikea/ikea_bilresa_dual_button/ikea_bilresa_light_control.yaml
```

## Why this repository has root files

- `README.md` explains what the repository contains.
- `LICENSE` makes reuse terms clear.
- `.gitignore` prevents accidental commits of editor and system files.

## License

MIT
