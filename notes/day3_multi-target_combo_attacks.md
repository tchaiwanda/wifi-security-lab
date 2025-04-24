# Day 3 - Multi-Target Combo Attacks

## Date:
April 24th, 2025

## Tools & Setup:
- **Board:** ESP8266 NodeMCU Devboard (Flipper Zero compatible)
- **Test network** Cyber-Lab (Guest Network)
- **Devices** Andriod, iPhone 12 Pro Max, Kali Linux VM, 2021 MacBook Pro
- **Firmware:** Deauther (accessed via web UI at `192.168.4.1`)
- **Firmware settings** default packet rate, 80% power.
- **Interface:** Web-based Deauther control panel

---

## Objective
Execute coordinated WiFi interference attacks using the ESP8266 Deauther, combining Beacon Spam and Deauthentication against multiple targets. This exercise simulates adversarial behavior in a controlled, isolated lab environment.

---

## Tasks Completed
1. Connected to ESP8266 Deauther WiFi (`Cyber-Lab`)
2. Accessed Deauther UI via browser at `192.168.4.1`
3. Performed a client scan to detect available APs and stations
4. Added multiple stations and APs to target list
5. Initiated **Combo Attack** (Beacon + Deauth) from web interface
6. Observed client disconnections and fake SSID broadcasts

---

## Key Concepts Learned
- **Beacon Spam:** Broadcasts fake SSIDs to confuse and distract nearby devices
- **Deauth Attack:** Sends disassociation frames to disconnect clients from APs
- **Combo Attack:** Combines both attacks for broader disruption
- Attack effectiveness depends on target OS/device behavior and signal strength
- Importance of **network isolation** to avoid unintended real-world impact

---

## Commands / UI Actions Used
- `Scan` – Discovered active stations and APs
- `Add` – Selected targets for attacks
- `Combo` – Started simultaneous Beacon + Deauth attacks
- `Stop` – Terminated attacks safely

---

## Observations
- Mac and Android devices handled deauth differently (Android reconnected faster)
- Some clients ignored beacon spam unless previously connected to similar SSID
- My guest lab network (`Cyber-Lab`) kept real devices isolated from main network
- No traffic leaked outside lab per Wireshark and router logs

---

## Next Steps
- Capture PCAPs of combo attacks for analysis
- Add detection and mitigation testing (monitor reauthentication behavior)
- Compare with USB WiFi adapter once it arrives
- Document fake SSID effectiveness on legacy vs modern clients

---

## Notes
This project is part of my hands-on cybersecurity lab while studying for **CompTIA Security+**. All tests were conducted in a fully isolated lab environment using only my own devices.
- 
