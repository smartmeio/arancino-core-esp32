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
To create a project with Visual Studio Code and PlatformIO it is necessary to initially create a project for a generic `ESP32` board and then modify the `platformio.ini` file in order to point to the Arancino packages. The `platformio.ini` file must be modififed in order to contains this configuration:
```
[env:arancino_esp32]
platform = https://github.com/smartmeio/platform-espressif32.git#5.2.0-arancino
framework = arduino
board = dfr_adapter
platform_packages = smartme-io/framework-arduinoespressif32-arancino@https://github.com/smartmeio/arancino-core-esp32.git
lib_deps = https://github.com/smartmeio/arancino-library
upload_port = ...
```
Any other used library must be included as dependency through `lib_deps` (as for the Arancino library) or saved under the `lib` folder; in the latter case the project structure should look like:
```
include
lib
+-- your_library
     +-- examples
     +-- include
     +-- keywords.txt
     +-- library.json
     +-- src
src
+-- main.cpp
test
```

Alternatively, you can set an extra directory in which to search for libraries. For example, if you want to include all the libraries installed in the Arduino IDE, you can specify it adding this lines to the `platformio.ini` configuration file:
```
lib_extra_dirs = ~/Arduino/libraries
```


## Enabling FreeRTOS support
In ESP32-based boards FreeRTOS is enabled by default and cannot be disabled.

## Espressif Documentation

You can use the [Arduino-ESP32 Online Documentation](https://docs.espressif.com/projects/arduino-esp32/en/latest/) to get all information about Arduino and ESP32.

### Supported Chips

Visit the [supported chips](https://docs.espressif.com/projects/arduino-esp32/en/latest/getting_started.html#supported-soc-s) documentation to see the list of current supported ESP32 SoCs.

### Decoding exceptions

You can use [EspExceptionDecoder](https://github.com/me-no-dev/EspExceptionDecoder) to get meaningful call trace.