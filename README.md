# TANTOF405 — custom Betaflight build

This repository contains a board configuration and GitHub Actions workflow for a custom Betaflight firmware build.

## Hardware configuration

- Flight controller: TANTOF405
- MCU: STM32F405
- Gyro/accelerometer: ICM42688P
- Barometer: DPS310
- OSD: MAX7456
- Onboard SPI flash: 8 MiB
- Motors: PA8, PA9, PC9, PC8
- SERVO1: PB3 (B03)
- SERVO2: PB1 (B01)
- Receiver default: UART2
- ESC telemetry default: UART5

PB3 is reserved for SERVO1 and is deliberately not assigned to LED_STRIP.

## Build

The workflow `.github/workflows/build-tantof405.yml` builds HEX and BIN firmware files using the pinned Betaflight source commit recorded in that workflow. It uploads the firmware and SHA-256 checksums as a GitHub Actions artifact.

The board configuration is in `board-config/configs/TANT/TANTOF405/config.h`.

**Do not flash without first checking the build log and confirming the detected sensors and resource map on the actual flight controller.**
