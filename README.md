# Definitive Guide to IR

This is the code for this YouTube video: https://youtu.be/gADIb1Xw8PE

It runs on ESP32. You have to use another library if you want to use it on an ESP8266 (https://github.com/markszabo/IRremoteESP8266) and replace the WiFi.h with ESP8266WiFi.h
Please comment credentials.h if you have no such file in your library folder.

The credentiald.h file just contains credentials:

#define CREDENTIALS 1
// WLAN
#define mySSID "***"
#define myPASSWORD "***"
