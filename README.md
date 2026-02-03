Brief description: This `README.md` explains the project that measures distance with an ultrasonic sensor on an Arduino Uno R4 WiFi using the provided `src/main.cpp` and `platformio.ini`.

```markdown
# Ultrasonic Distance Sensor — Arduino Uno R4 WiFi

Project to measure distance using an ultrasonic sensor (e.g. HC\-SR04) connected to an `Arduino Uno R4 WiFi`. Uses the code in `src/main.cpp` and the build configuration in `platformio.ini`.

## Files
1. `src/main.cpp` — Arduino sketch that triggers the ultrasonic sensor, measures echo pulse duration and prints distance over Serial.
2. `platformio.ini` — PlatformIO environment configuration for the Uno R4 WiFi.

## Hardware
1. Arduino Uno R4 WiFi
2. Ultrasonic sensor (HC\-SR04 or compatible)
3. Jumper wires
4. Breadboard (optional)
5. Optional: resistor divider or level shifter for the echo pin if required

## Wiring
1. VCC -> `5V` on `Arduino Uno R4 WiFi`
2. GND -> `GND`
3. TRIG -> digital pin `9`
4. ECHO -> digital pin `10` (use a 1k/2k resistor divider or level shifter if your board requires 3.3V signals)

## Software / Prerequisites
1. Windows
2. CLion with PlatformIO plugin or PlatformIO Core (CLI)
3. PlatformIO installed and configured for `Arduino` framework

Example `platformio.ini` environment (adjust `board` name if needed):
```ini
[env:uno_r4_wifi]
platform = atmelmegaavr
board = arduino_uno_r4_wifi
framework = arduino
monitor_speed = 9600
```

## Build & Upload (PlatformIO CLI)
1. Open a terminal in the project folder.
2. Build: `pio run`
3. Upload: `pio run -t upload`
4. Serial monitor: `pio device monitor -b 9600`

Or use the PlatformIO UI in CLion to Build / Upload / Monitor.

## How the code works (summary)
1. `TRIG` pin is set LOW, then HIGH for 10 microseconds to send a pulse.
2. `pulseIn()` measures the time (in microseconds) that `ECHO` is HIGH.
3. Distance is computed as `distance = duration * 0.034 / 2` (speed of sound ~ 0.034 cm/µs).
4. Distance is printed over Serial at `9600` baud once per second.

## Troubleshooting
1. No readings: check wiring, power, and correct pins.
2. Constant 0 or large values: ensure `TRIG` pulse is generated and `ECHO` can reach the board voltage safely.
3. Wrong board error: confirm `board` in `platformio.ini` matches your device.

## License
MIT
```
