# Water Alarm

Minimal Home Assistant blueprint for critical water leak alerts with repeat notifications and optional power-off.

## Quick Install

[![Import Blueprint](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Fkemoxi%2Fhaos-blueprints%2Fmain%2Fwater-alarm%2Fcritical_water_leak_alarm.yaml)

## Manual Install

- Import this raw GitHub URL in Home Assistant:
  `https://raw.githubusercontent.com/kemoxi/haos-blueprints/main/water-alarm/critical_water_leak_alarm.yaml`
- Or copy the YAML file manually to:
  `config/blueprints/automation/`

## Overview

This blueprint sends critical mobile notifications when water is detected, repeats the alert until the sensor is dry again, and can optionally switch off a smart plug or device.

## Inputs

- **Water sensor** — binary sensor that reports water detection
- **Mobile devices to notify** — one or more phones with the Home Assistant Companion App
- **Alarm title** — title of the first notification
- **Alarm message** — message of the first notification
- **Repeat message** — repeated alert text while water is still detected
- **Repeat interval** — delay between repeated notifications
- **Optional switch to turn off** — smart plug or switch to power off when water is detected

## Tested with

- Tuya Smart Water Leak Sensor Flood Model CB32
