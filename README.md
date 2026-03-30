# HA_ProcessMining_Addon
Brings Process Mining to Home Assistant as an Add-on.

This repository is a Home Assistant deployment wrapper for the actual
[SmartHomeProcessMining](https://github.com/FelixMarschall/SmartHomeProcessMining)
application.

## Why Process Mining on Smart Home Data?
Process mining turns event logs into understandable models of real-world behavior.
Smart homes already generate rich logs through device state changes and automations,
so you can use these techniques to:

- Discover real routines and occupancy patterns
- Spot anomalies or inefficiencies in automation flows
- Optimize energy usage based on actual device sequences
- Visualize how daily processes evolve over time

The motivation for this project is to bring these analytical insights to Home
Assistant users so they can understand and improve their smart home behavior
using the existing logbook data.

## Installation
[![Open your Home Assistant instance and show the add add-on repository dialog with a specific repository URL pre-filled.](https://my.home-assistant.io/badges/supervisor_add_addon_repository.svg)](https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https%3A%2F%2Fgithub.com%2FFelixMarschall%2FHA_ProcessMining_Addon)

Guide for Home Assistant Add-on configuration: [DOCS](process_management/DOCS.md)

Installation without Home Assistant environment: [SmartHomeProcessMining](https://github.com/FelixMarschall/SmartHomeProcessMining)

## Project Structure
This repository mainly contains the Home Assistant add-on packaging and points to
the real application via a git submodule.

- `process_management/`: Home Assistant add-on definition, Dockerfile, and `config.yaml`.
- `process_management/app/SmartHomeProcessMining/`: git submodule with the actual
  process mining application code.
- `repository.yaml`: metadata for the Home Assistant add-on repository.

Because the application lives in the submodule, you need to initialize it when
working locally:

```bash
git submodule update --init --recursive
```
