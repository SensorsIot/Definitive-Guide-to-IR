# Definitive Guide to IR

[![MIT License](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![GitHub stars](https://img.shields.io/github/stars/SensorsIot/Definitive-Guide-to-IR)](https://github.com/SensorsIot/Definitive-Guide-to-IR/stargazers)
[![YouTube](https://img.shields.io/badge/YouTube-Video-red?logo=youtube)](https://youtu.be/gADIb1Xw8PE)

![ESP32](https://img.shields.io/badge/ESP32-Supported-green?logo=espressif)
![Arduino](https://img.shields.io/badge/Arduino-Compatible-00979D?logo=arduino)

This is the code for this YouTube video: https://youtu.be/gADIb1Xw8PE

## 📥 Installation

1. Download this repository (Code → Download ZIP)
2. Extract the ZIP file
3. Copy the **ESP32-IRremote** folder to your Arduino libraries folder:
   - 🪟 Windows: `Documents\Arduino\libraries\`
   - 🍎 macOS: `~/Documents/Arduino/libraries/`
   - 🐧 Linux: `~/Arduino/libraries/`
4. Restart the Arduino IDE
5. Open the example sketch from File → Examples → IRremote

> ⚠️ **Important:** You need to copy the `ESP32-IRremote` folder itself, not the entire repository folder.

## 🔧 Platform Compatibility

| Platform | Status | Library to Use |
|----------|--------|----------------|
| ESP32 | ✅ Supported | **ESP32-IRremote** (this repo) |
| ESP8266 | ⚠️ Use alternative | [IRremoteESP8266](https://github.com/markszabo/IRremoteESP8266) |

> ❌ **Do NOT use IRremoteESP8266 on ESP32 with this project!** It may cause crashes when sending IR signals. Use the `ESP32-IRremote` library from this repository instead.

## 📡 IRMQTT_ESP32

The `IRMQTT_ESP32` folder contains an MQTT-enabled IR transceiver sketch that allows you to:

- **Receive** IR codes and publish them to an MQTT broker
- **Send** IR codes by subscribing to MQTT commands

### Wiring

| Function | GPIO Pin |
|----------|----------|
| IR Receiver | GPIO 14 |
| IR Sender | GPIO 5 |
| Status LED | GPIO 2 |

### MQTT Topics

| Topic | Direction | Description |
|-------|-----------|-------------|
| `IR/key` | Publish | Received IR codes are published here |
| `IR/command` | Subscribe | Send IR codes by publishing here |
| `IR/service` | Publish | Status messages |

### JSON Message Format

```json
{"type":"3", "value":"1303526340", "length":"32"}
```

| Field | Description |
|-------|-------------|
| `type` | IR protocol (1=RC5, 2=RC6, 3=NEC, 4=Sony, 5=Panasonic, 6=JVC) |
| `value` | The IR code value |
| `length` | Bit length of the code |

### Supported Protocols

NEC, Sony, Panasonic, JVC, RC5, RC6

## ⚙️ Configuration

Please comment out the `credentials.h` include if you have no such file in your library folder.

The credentials.h file contains your WiFi credentials:

```cpp
#define CREDENTIALS 1
// WLAN
#define mySSID "your-wifi-name"
#define myPASSWORD "your-wifi-password"
```

Set your MQTT broker IP in the sketch:

```cpp
IPAddress server(192, 168, 0, 203);
```
