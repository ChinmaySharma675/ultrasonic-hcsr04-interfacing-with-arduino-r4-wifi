# Ultrasonic Distance Sensor with Arduino UNO R4 WiFi

Project that measures distance using an ultrasonic sensor (e.g. HC-SR04) connected to an Arduino UNO R4 WiFi and prints results to the serial monitor.

## Files
- `src/main.cpp` \- Arduino sketch that triggers the ultrasonic pulse, reads echo via `pulseIn`, computes distance in cm and prints it at 9600 baud.
- `platformio.ini` \- PlatformIO project configuration used to build and upload the sketch.

## Hardware
- Arduino UNO R4 WiFi
- Ultrasonic sensor (HC-SR04 or compatible)
- Jumper wires
- Breadboard (optional)

Important: confirm sensor operating voltage and UNO R4 WiFi pin voltage compatibility before connecting power.

## Wiring
- Sensor VCC \- connect to 5V (or as required by your sensor, check datasheet)
- Sensor GND \- connect to board GND
- Sensor TRIG \- connect to digital pin D9
- Sensor ECHO \- connect to digital pin D10

Adjust pins in `src/main.cpp` if different pins are used.

## PlatformIO (example `platformio.ini`)
Use PlatformIO to build and upload. Replace the `board` value with the correct PlatformIO board ID if necessary.

```ini
[env:uno_r4_wifi]
platform = atmelsam
board = uno_r4_wifi
framework = arduino
monitor_speed = 9600
