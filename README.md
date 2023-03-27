# Arancino core for the ESP32, ESP32-S2, ESP32-S3 and ESP32-C3

![Release](https://img.shields.io/github/v/release/smartmeio/arancino-esp32-core?style=plastic)

This core is a fork of the [Arduino core for ESP32](https://github.com/espressif/arduino-esp32) modified to support the functionality of the Arancino architecture.

# Supported Boards
* Arancino DFR adapter

## Installation on Arduino IDE

This core is available as a package in the Arduino IDE cores manager. If you want to install it:

  1. Open the **Preferences** of the Arduino IDE.
  2. Add this URL `https://raw.githubusercontent.com/smartmeio/arancino-boards/master/package_smartmeio_index.json` in the **Additional Boards Manager URLs** field, and click OK.
  3. Open the **Boards Manager** (menu `Tools` -> `Board` -> `Board Manager...`)
  4. Install **Arancino ESP32 Boards**
  5. Select one of the boards under **Arancino ESP32 Boards** in `Tools` -> `Board` menu

## Installation on PlatformIO and Visual Studio Code
_WIP_

## Enabling FreeRTOS support
In ESP32-based boards FreeRTOS is enabled by default and cannot be disabled.

## Espressif Documentation

You can use the [Arduino-ESP32 Online Documentation](https://docs.espressif.com/projects/arduino-esp32/en/latest/) to get all information about Arduino and ESP32.

### Supported Chips

Visit the [supported chips](https://docs.espressif.com/projects/arduino-esp32/en/latest/getting_started.html#supported-soc-s) documentation to see the list of current supported ESP32 SoCs.

### Decoding exceptions

You can use [EspExceptionDecoder](https://github.com/me-no-dev/EspExceptionDecoder) to get meaningful call trace.
