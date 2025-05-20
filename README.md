# 🔒 Fingerprint-Based Door Lock System using Adafruit Fingerprint Sensor

This project demonstrates a biometric door lock system using the **Adafruit R305 Fingerprint Sensor** and a microcontroller with support for multiple serial ports(Raspberry Pi Pico). When a registered fingerprint is detected, the system toggles a **relay** (connected to GPIO 26) to control an electronic door lock.

---

## 🚀 Features

- Fingerprint matching using the Adafruit fingerprint sensor
- Relay toggling for locking/unlocking a door
- Serial monitoring of fingerprint sensor status and debug logs
- Uses `HardwareSerial` for reliable communication with the fingerprint sensor

---

## 🛠️ Hardware Requirements

- Microcontroller with multiple hardware serial ports 
- Adafruit-compatible fingerprint sensor (R305)
- Relay module
- Jumper wires
- Power supply (5V for sensor and relay)
  

---

## 🔌 Pin Configuration

| Component           | Connection         |
|--------------------|--------------------|
| Fingerprint Sensor TX | Microcontroller RX (e.g., Serial1 RX) |
| Fingerprint Sensor RX | Microcontroller TX (e.g., Serial1 TX) |
| Fingerprint Sensor VCC | 5V |
| Fingerprint Sensor GND | GND |
| Relay IN            | GPIO 26            |
| Relay VCC           | 5V                 |
| Relay GND           | GND                |

---

## 📦 Libraries Used

- [`Adafruit_Fingerprint`](https://github.com/adafruit/Adafruit-Fingerprint-Sensor-Library)
- `HardwareSerial` (built into Arduino/ESP32 environment)



---

## 🧠 How It Works

1. On startup, the sensor is initialized and checked.
2. If fingerprints are already enrolled, the system waits for a valid finger.
3. When a finger is placed:
   - The sensor captures and processes the fingerprint.
   - If a match is found:
     - GPIO 26 toggles, activating or deactivating the relay.
     - Match details are printed to the Serial Monitor.
   - If no match is found, the system continues to wait.



