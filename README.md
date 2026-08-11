# Hydrosnooze Controller

Replacement hardware and ESPHome firmware for the controller of Hydrosnooze-compatible water-cooled/heated mattress systems.

This project replaces the original controller with an open, ESPHome-based controller while retaining the original pump, heater, cooler, fans, temperature sensor and water-level protection.

## Features

- ESPHome-based controller
- Wi-Fi and Home Assistant integration
- Temperature regulation from 15–55 °C
- Separate heating and cooling modes
- Proportional temperature regulation using slow PWM
- Pump interlock for heating and cooling
- Fan control with minimum speed during cooling
- Fan tachometer monitoring
- Pump current monitoring
- Water-level / float-switch protection
- Automatic thermal shutdown on:
  - pump failure
  - low water level
  - temperature outside 10–60 °C
- Controlled shutdown with post-run pump and fan operation
- OTA firmware updates
- Web interface and ESPHome API

## Hardware

The replacement controller is based on a **Seeed Studio XIAO ESP32-C3** and an **MCP23017** GPIO expander.

The controller interfaces with the existing Hydrosnooze hardware for:

- Pump control
- Heater control
- Peltier cooler control
- Fan PWM
- Fan tachometer
- Water temperature measurement
- Water-level detection
- Pump current measurement

The project includes the hardware design and documentation required to build the replacement controller.

## Software

The firmware is written for [ESPHome](https://esphome.io/) and is intended to integrate directly with Home Assistant.

The ESP32 handles the actual thermal regulation and hardware safety functions locally. Home Assistant can be used for higher-level automation, scheduling and user control.

## Why?

The original Hydrosnooze controller provides limited control and integration options. This project replaces it with a controller that is:

- locally controllable
- Home Assistant compatible
- configurable
- repairable
- extensible

The original hardware remains responsible for the high-voltage and power electronics where appropriate; this project provides the replacement low-voltage control electronics and firmware.

## Repository

```text
hardware/    Hardware design files and documentation
firmware/    ESPHome configuration