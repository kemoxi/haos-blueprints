# IKEA Bilresa Dual Button

One remote. Light switching, hold-to-dim controls and two color-temperature presets.

## Quick Install

[![Import blueprint](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Fkemoxi%2Fhaos-blueprints%2Fmain%2Fikea-bilresa-dual-button%2Fikea-bilresa-dual-button.yaml)

After importing, create an automation and select the five entities listed below.

## Requirements

- An IKEA Bilresa setup exposing two `event` entities and two `sensor` entities.
- Event types matching `multi_press_1`, `multi_press_2` and `long_press` as used by the blueprint.
- Hold sensors reporting the state `1` while the relevant button is held.
- A target light supporting brightness control and the 2700 K / 4000 K color-temperature presets.

Compatibility depends on the entities and events exposed by your integration, not only on the remote's product name. This is not a generic action-entity or MQTT-topic blueprint.

## Controls

| Button | Gesture | Result |
| --- | --- | --- |
| Upper / Button 1 | Single press | Toggle the light with a one-second transition |
| Upper / Button 1 | Hold | Increase brightness in 8-percentage-point steps |
| Lower / Button 2 | Hold | Decrease brightness in 8-percentage-point steps while the reported brightness is above 10 on Home Assistant's 0–255 scale |
| Lower / Button 2 | Double press | Switch between the warm and cool presets below |

Dimming repeats with a 200 ms delay and a 0.2-second light transition while the relevant hold sensor remains `1`.

## Inputs

All five inputs are required.

| Input in Home Assistant | Entity type | Select |
| --- | --- | --- |
| Light | `light` | The light to control |
| Event Button 1 | `event` | The upper button's event entity |
| Sensor Button 1 | `sensor` | The upper button's hold-state sensor |
| Event Button 2 | `event` | The lower button's event entity |
| Sensor Button 2 | `sensor` | The lower button's hold-state sensor |

## Warm and cool presets

| Preset | Color temperature | Brightness |
| --- | --- | --- |
| Warm | 2700 K | 40% |
| Cool | 4000 K | 100% |

A lower-button double press selects Warm when the current color temperature is above 3000 K; otherwise it selects Cool. It also sets the corresponding brightness with a one-second transition.

These are direct light settings, not Home Assistant scene entities. The presets and dimming step size are fixed in the YAML and are not configurable inputs.

## Manual Install

Paste this URL into Home Assistant's blueprint import dialog:

```text
https://raw.githubusercontent.com/kemoxi/haos-blueprints/main/ikea-bilresa-dual-button/ikea-bilresa-dual-button.yaml
```

Alternatively, copy [`ikea-bilresa-dual-button.yaml`](ikea-bilresa-dual-button.yaml) to:

```text
<config>/blueprints/automation/kemoxi/ikea-bilresa-dual-button.yaml
```

Then create an automation from the blueprint and select the required entities.

## Behavior to know

The automation uses `mode: single`: additional triggers are ignored while an action sequence is running, including a hold-to-dim loop. A lower-button single press has no assigned light action in this blueprint.

[All blueprints](../README.md) · [MIT license](../LICENSE)
