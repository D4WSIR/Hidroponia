# Hidroponia



# ESP32 Relay Control via Bluetooth

This project allows you to control **2 relays** with an **ESP32** using **Classic Bluetooth** and a terminal app on an Android phone.

---

## 🌱 Application: Hydroponics and Garden Automation

This system can be integrated into a **hydroponic project** or **urban garden automation**, enabling:

- 💧 Control of **water flow** with a **water pump** connected to a relay
- 🔆 Control of **artificial lighting** to simulate the sunlight cycle
  
---

## 🧰 Required Materials

- 1x ESP32 Dev Kit  
- 1x 2-channel relay module (5V, SRD-05VDC-SL-C)  
- Jumper wires  
- 5V power supply (optional for more stable relay power)  
- Android phone with Bluetooth  

---

## ⚡ Wiring Diagram

| ESP32 | Relay Module | Function            |
|--------|-----------------|---------------------|
| D15    | IN1             | Controls Relay 1    |
| D2     | IN2             | Controls Relay 2    |
| GND    | GND             | Ground              |
| 5V     | VCC             | Power to relay module |

💡 You may add a **1kΩ resistor** between the ESP32 pin and the relay INx pin for protection.

---

## 🧠 How It Works

- The ESP32 presents itself over Bluetooth as `ESP32_2Relays`.
- You connect via an app and send text commands.
- The relay is **activated with LOW (0V)** signal → a **LOW GPIO** triggers the relay.

---

## 📱 Android App

1. Download **Serial Bluetooth Terminal** app:  
   [Link on Play Store](https://play.google.com/store/apps/details?id=de.kai_morich.serial_bluetooth_terminal)

2. Turn on Bluetooth on your phone  
3. Pair with `ESP32_2Relays` (PIN: `1234` or `0000`)  
4. Open the app and connect to the device  
5. Send the following commands:

| Command | Action            |
|---------|-------------------|
| `A`     | Turns Relay 1 ON  |
| `B`     | Turns Relay 1 OFF |
| `C`     | Turns Relay 2 ON  |
| `D`     | Turns Relay 2 OFF |

---

## 📝 Notes

- The ESP32 blue LED may turn on together with relay 2 (GPIO 2) — this is normal.
- For iPhone compatibility, the project would need to be adapted to use **Bluetooth Low Energy (BLE)**.
