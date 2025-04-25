# Day 4 – MAC Address Fingerprinting

## Objective
Explore MAC address fingerprinting using the ESP8266 Deauther. Learn how different device types reveal identifiable MAC address patterns and analyze their connection behavior on WiFi networks.

---

## Tools & Devices
- **Board:** ESP8266 NodeMCU Devboard (Flipper Zero compatible)
- **Firmware:** Deauther (Web UI accessible at `192.168.4.1`)
- **Devices Tested:** 
  - Android Phone
  - iPhone
  - MacBook
- **Lab Network:** Isolated guest WiFi (`Cyber-Lab`)

---

## Tasks Completed
1. **Connected to ESP8266 Deauther UI**
   - Accessed the admin panel at `192.168.4.1` via browser
2. **Scanned for Devices**
   - Used the **Clients** and **Scan** tab to detect nearby MAC addresses
3. **Recorded MAC Patterns**
   - Compared prefix patterns (OUI) and randomized vs static MAC behavior
   - Identified vendor info using MAC address lookup tools
4. **Analyzed MAC Behavior**
   - Observed MAC address changes on iOS/Android during probing and reconnecting
   - Noted differences in MAC permanence and usage per OS

---

## Key Concepts Learned
- **MAC Fingerprinting:** Identifying devices by analyzing MAC address format and behavior
- **OUI (Organizationally Unique Identifier):** First 3 bytes of a MAC address indicate manufacturer
- **MAC Randomization:** Modern OSs (esp. iOS/Android) often use randomized MACs to prevent tracking
- **Device-Specific Patterns:** Different vendors use identifiable patterns, especially on legacy devices

---

## Observations
- iPhones and newer Android devices used randomized MACs while probing
- Windows laptop revealed static MAC when connecting
- MacBook rotated MACs depending on connection context (e.g. auto-connect vs manual)
- The ESP8266’s scan mode captured probe requests effectively
- Identifying devices based solely on MAC is unreliable without additional fingerprinting methods

---

## Tools/Lookups Used
- Deauther Web UI Scan → Detected clients/APs
- MAC lookup tools like [macvendors.com](https://macvendors.com)
- Compared MACs to known OUIs (Organizationally Unique Identifiers)

---

## Reflections
- MAC fingerprinting has forensic potential, but randomization limits its effectiveness
- Combining MAC fingerprinting with traffic behavior or hostname data can improve attribution
- Essential to perform these tests in a safe lab where privacy and consent are managed

---

## Next Steps
- Collect multiple MAC samples per device type and OS version
- Begin testing behavior during roaming or network switching
- Build a small script to categorize MACs by vendor in future projects
- Research passive monitoring tools (Kismet, Wireshark) to supplement findings

---

## Notes
This activity is part of a self-guided hands-on cybersecurity lab. The entire environment is isolated and all devices used are my own. I’m using this lab to reinforce concepts while studying for the **CompTIA Security+** certification.
