# Water Alarm

Water-leak notifications with repeat alerts and optional switch-off.

## Quick Install

[![Import blueprint](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Fkemoxi%2Fhaos-blueprints%2Fmain%2Fwater-alarm%2Fcritical-water-leak-alarm.yaml)

After importing, create an automation, select your water sensor and mobile devices, and review the messages and optional switch.

## Requirements

- A water-leak `binary_sensor` that changes to `on` when water is detected and returns to `off` when dry.
- One or more mobile devices registered through the Home Assistant Companion App (`mobile_app`).
- Working notification services for the selected devices. The blueprint derives each `notify.mobile_app_...` service name from the device name, so verify that the resulting service exists in your setup.
- Optionally, a `switch` entity to turn off when water is detected.

The notification payload includes iOS-style critical-alert sound settings. Critical sound behavior depends on the receiving app, operating system and permissions; this documentation does not promise identical behavior on every phone.

## Inputs

| Input in Home Assistant | Purpose | Default / selection |
| --- | --- | --- |
| Water sensor | Detect a leak | Required `binary_sensor` |
| Mobile devices to notify | Receive initial and repeated alerts | Select one or more `mobile_app` devices |
| Alarm title | Title used for initial and repeated notifications | `🚨 WASSERALARM!` |
| Alarm message | Initial notification text | `Wasser erkannt – bitte sofort prüfen!` |
| Repeat message | Repeated notification text, with the current time appended | `🚨 WASSERALARM! Sensor meldet weiterhin Wasser.` |
| Repeat interval | Delay after a repeated notification round | `00:01:00` |
| Optional switch to turn off | Turn off a switch after the initial notification round | No switch selected |

The notification text is editable; the default messages are German.

## How it works

1. The sensor changes to `on`.
2. Initial notifications are sent to the selected devices, with a two-second delay after each device notification.
3. The optional switch-off action is evaluated after the initial notification round.
4. While the sensor remains `on`, repeated notifications are sent to the selected devices. Each repeated message includes a timestamp.
5. After each repeated notification round, the configured repeat interval elapses before the next sensor check.

The first repeat round can start immediately after the initial round and switch-off step if the sensor is still wet. The repeat interval is not a delay before the first alert and is not an exact per-device delivery interval: notification processing and per-device delays add time.

There is no dedicated dry-again notification or automatic switch-on action. Drying the sensor does not cancel a round that has already started. The automation uses `mode: restart`.

## Manual Install

Paste this URL into Home Assistant's blueprint import dialog:

```text
https://raw.githubusercontent.com/kemoxi/haos-blueprints/main/water-alarm/critical-water-leak-alarm.yaml
```

Alternatively, copy [`critical-water-leak-alarm.yaml`](critical-water-leak-alarm.yaml) to:

```text
<config>/blueprints/automation/kemoxi/critical-water-leak-alarm.yaml
```

Then create an automation and configure its inputs.

## Test your setup

Before relying on the automation, check notification delivery, repeat behavior and the optional switch-off action in your own setup. Failed notification actions can prevent subsequent actions from running, including switch-off. Choose only a switch that is appropriate to turn off in a leak scenario. Notifications depend on Home Assistant, your network and the receiving device; they are not a guaranteed safety system.

## Reported tested device

- Tuya Smart Water Leak Sensor Flood Model CB32, as listed in the previous repository documentation.

This is not a guarantee of compatibility with every integration or mobile-device configuration.

[All blueprints](../README.md) · [MIT license](../LICENSE)
