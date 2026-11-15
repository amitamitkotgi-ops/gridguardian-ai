---
name: esp32-iot-telemetry
description: ESP32 firmware, sensor acquisition, calibration, telemetry and Wi-Fi integration for SOLARIS AI. Use when implementing firmware, wiring plans, sensor drivers or device-to-backend communication.
---

# ESP32 IoT Telemetry Skill

## Before implementation
Confirm exact ESP32 board, pin map, sensor part numbers, bus voltage, supply requirements, expected current/voltage range and wiring topology. Check datasheets before selecting pins or circuits.

## Firmware principles
- Keep acquisition and network communication non-blocking where practical.
- Use bounded retries and explicit sensor/network error states.
- Validate readings and flag out-of-range or stale values.
- Avoid blocking delays in time-critical acquisition.
- Use watchdog-safe loops and safe startup defaults.
- Never drive loads directly from GPIO; use properly rated driver/relay hardware and protection.
- Keep secrets/configuration out of firmware source where possible.

## Telemetry contract
Send device_id, plant_id, UTC timestamp, schema_version, firmware_version, operating_mode, values with units and quality flags. Include explicit simulation/physical mode. Do not transmit fabricated sensor readings as physical measurements.

## Verification
Test sensor readout, calibration, Wi-Fi loss/recovery, backend timeout, malformed payload, reboot and safe failure behaviour. Record actual test evidence.
