# Corridor Light

ESP8285 corridor wall-switch controller with relay control and smart-bulb event pulses.

## What it does

Uses the shared wall-switch gesture logic to emit Home Assistant button pulses for smart bulbs and control relay power for sustained position changes. Configure a Home Assistant automation to respond to Wall Button Pulse.

## Hardware and configuration

- ESPHome entry point: [`corridorlight.yaml`](corridorlight.yaml).
- Board/profile: `esp8285`.
- GPIO assignments, calibration constants and exposed entities are defined in the YAML. Match them to your hardware before use.
- Included local dependencies: `packages/wall_switch_controls.yaml`, `wall_switch_logic.h`.

## Setup

1. Keep the repository directory structure when copying it to ESPHome Device Builder.
2. Copy `secrets.example.yaml` to `secrets.yaml`; enter your Wi-Fi settings, unique OTA password and API encryption key. Generate an API key with `openssl rand -base64 32`. Set any BSSID/static-network/web-login placeholders for your own installation.
3. Review pins, sensor calibration, network settings and any Home Assistant entity references.
4. Validate with `esphome config corridorlight.yaml`, then build with `esphome compile corridorlight.yaml`. Choose an ESPHome version compatible with the source; the publication check uses ESPHome 2026.9.1.
5. Flash only the intended board after checking its wiring and configuration.

`secrets.yaml` and build outputs are ignored by Git. Fonts referenced with `gfonts://` require download access during preparation/build.

## Source and publication notes

Snapshot of the stored Home Assistant ESPHome source taken on **2026-10-27**. This is not proof of which firmware is currently flashed. Creating this repository does not upload firmware or change a live device.

- Credentials and network settings moved to `!secret` references.
- Atlantis/Stargate radio packages and their substitutions omitted from this standalone device repository.

See [VALIDATION.md](VALIDATION.md) for the publication checks and their limits.
