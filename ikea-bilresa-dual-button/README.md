# IKEA Bilresa Dual Button

Minimal Home Assistant blueprint for the IKEA Bilresa dual-button remote.

## Quick Install

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Fkemoxi%2Fhaos-blueprints%2Fmain%2Fikea-bilresa-dual-button%2Fikea-bilresa-dual-button.yaml)

## Manual Install

- Import this raw GitHub URL in Home Assistant:
  `https://raw.githubusercontent.com/kemoxi/haos-blueprints/main/ikea-bilresa-dual-button/ikea-bilresa-dual-button.yaml`
- Or copy the YAML file manually to:
  `config/blueprints/automation/`

## Overview

This blueprint provides simple button-based control for the IKEA Bilresa dual-button remote.

## Inputs

- **Button / remote entity** — the IKEA Bilresa remote used as trigger
- **Target light** — the light entity to control
- **Warm / cool scene or mode targets** — optional target behavior depending on your setup

## Actions

- Toggle light
- Brightness up
- Brightness down
- Toggle warm / cool scene
