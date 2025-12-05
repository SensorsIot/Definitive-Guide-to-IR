# ESP32-IRremote Library

This is a modified version of the IRremote library with ESP32 support.

## 📥 Installation

> ⚠️ **Important:** Do NOT download from the Releases page of the original IRremote repo. Use the parent repository instead.

**See the main [README](../README.md) for installation instructions.**

Quick steps:
1. Download the parent repository: https://github.com/SensorsIot/Definitive-Guide-to-IR
2. Copy this entire `ESP32-IRremote` folder to your Arduino libraries folder
3. Restart Arduino IDE

## Supported Boards

- Arduino Uno / Mega / Leonardo / Duemilanove / Diecimila / LilyPad / Mini / Fio / Nano etc.
- Teensy 1.0 / 1.0++ / 2.0 / 2++ / 3.0 / 3.1 / Teensy-LC
- Sanguino
- ATmega8, 48, 88, 168, 328
- ATmega8535, 16, 32, 164, 324, 644, 1284
- ATmega64, 128
- ATtiny 84 / 85
- ESP32

### Hardware specifications

| Board/CPU | Send Pin | Timers |
|-----------|----------|--------|
| ATtiny84 | **6** | **1** |
| ATtiny85 | **1** | **TINY0** |
| ATmega8 | **9** | **1** |
| Atmega32u4 | 5, 9, **13** | 1, 3, **4** |
| ATmega48, ATmega88, ATmega168, ATmega328 | **3**, 9 | 1, **2** |
| ATmega1284 | 13, 14, 6 | 1, **2**, 3 |
| ATmega164, ATmega324, ATmega644 | 13, **14** | 1, **2** |
| ATmega8535, ATmega16, ATmega32 | **13** | **1** |
| ATmega64, ATmega128 | **13** | **1** |
| ATmega1280, ATmega2560 | 5, 6, **9**, 11, 46 | 1, **2**, 3, 4, 5 |
| ESP32 | configurable | **1** |
| Teensy 1.0 | **17** | **1** |
| Teensy 2.0 | 9, **10**, 14 | 1, 3, **4_HS** |
| Teensy++ 1.0 / 2.0 | **1**, 16, 25 | 1, **2**, 3 |
| Teensy 3.0 / 3.1 | **5** | **CMT** |
| Teensy-LC | **16** | **TPM1** |

## FAQ

**IR does not work with Neopixels (WS2811/WS2812/WS2812B)**

Whether you use the Adafruit Neopixel lib or FastLED, interrupts get disabled on many lower end CPUs. This stops the IR interrupt handler from running. See [this page from Marc MERLIN](http://marc.merlins.org/perso/arduino/post_2017-04-03_Arduino-328P-Uno-Teensy3_1-ESP8266-ESP32-IR-and-Neopixels.html) for solutions.

## Original Copyright

Based on IRremote by Ken Shirriff (Copyright 2009-2012)
