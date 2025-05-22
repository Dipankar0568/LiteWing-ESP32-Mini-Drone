# LiteWing - ESP32 Based Mini Drone 🚁

LiteWing is a compact, open-source, DIY programmable drone based on the ESP32 platform. It can be controlled via Wi-Fi using a mobile app or programmed with Python using `cfclient` and `cflib`.

## ✨ Features

- ESP32 based flight controller
- WiFi Controlled via ESP-Drone app
- Compatible with `cfclient` + `cflib` Python API
- MPU6050 for motion control & stability
- Height hold and gesture control (via upgrades)
- All-in-one PCB (no 3D printed frame needed)
- Built-in battery charging and USB interface
- Debug LEDs (calibration, WiFi, battery status)
- Android & iOS App Support
- Open-source design and firmware

## 🧩 Components Required

| Component                      | Quantity | Notes                            |
|-------------------------------|----------|----------------------------------|
| ESP32 Wroom Module            | 1        | Core controller                  |
| MPU6050 IMU                   | 1        | Stability sensor (I2C)           |
| CP2102N USB-UART              | 1        | USB programming interface        |
| TP4056 Li-ion Charger         | 1        | Battery charging                 |
| MIC5219-3.3YM5 LDO Regulator  | 1        | Power regulation                 |
| AO3401 P-MOSFET               | 1        | Power path switching             |
| 2N7002DW N-MOSFET             | 1        | Auto-reset circuit               |
| SI2302 N-MOSFET               | 4        | Motor drivers                    |
| Coreless Motors (720)         | 4        | Propulsion                       |
| 55mm Propellers (CW & CCW)    | 2+2      | Lift                             |
| LiPo Battery 1300mAh 30C      | 1        | Power source                     |
| Type-C USB Connector          | 1        | Charging + Programming           |
| PCB, LEDs, Diodes, Resistors  | Misc     | As per schematics                |

👉 Full **[BOM and Schematic](./Hardware/Schematics.pdf)** included in the repo.

## 🔧 Build Instructions

1. Solder all components on the **custom PCB**.
2. Connect motors and propellers (see Propeller_Direction.png).
3. Flash the firmware (see below).
4. Connect via ESP-Drone App or Python.

## 📦 Firmware Flashing

### Option 1: ESP-IDF Build
```bash
git clone https://github.com/Circuit-Digest/ESP-Drone.git
cd ESP-Drone/Firmware/esp-drone
idf.py menuconfig
idf.py -p /dev/ttyUSB0 flash
