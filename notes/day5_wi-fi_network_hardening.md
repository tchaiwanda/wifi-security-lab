# Day 5 – WiFi Network Hardening

## Objective
Study and apply WiFi network security best practices to harden access points, reduce exposure to common attacks (deauthentication, beacon spam, MAC spoofing), and secure the lab environment used for offensive testing.

---

## Tools & Devices
- **Router:** NETGEAR (lab router)
- **Interfaces:** Admin Web UI
- **Devices:** Test phone, MacBook, ESP8266 Deauther
- **Lab Network:** Cyber-Lab Guest WiFi

---

## Tasks Completed
1. **Secured SSID & Password**
   - Renamed default SSID to a non-identifiable name
   - Set a strong, complex WPA2 password

2. **Disabled WPS (Wi-Fi Protected Setup)**
   - Eliminated WPS attack vector by turning off WPS in router settings

3. **MAC Filtering (Optional)**
   - Enabled MAC filtering to allow only whitelisted lab devices (temporary)

4. **Firmware & Admin Access**
   - Updated router firmware to the latest version
   - Changed default router admin password and disabled remote access

5. **Guest Network Isolation**
   - Verified that the guest network cannot access main LAN
   - Ensured no inter-client communication (AP isolation enabled)

6. **ESP8266 Testing**
   - Launched deauth & beacon spam tests against hardened WiFi to measure resiliency
   - Logged results from Wireshark and Deauther interface

---

## Key Concepts Learned
- **SSID Cloaking Is Not Security:** Hiding an SSID doesn’t stop broadcast attacks
- **WPS Is a Weakness:** Should always be disabled due to brute-force risks
- **Admin Access & Firmware:** Keeping routers updated is critical against exploits
- **Guest Network Isolation:** Essential to contain testing to specific subnets

---

## Observations
- Disabling WPS removed vulnerability to Pixie Dust-style attacks
- MAC filtering helped during tests but is not scalable or foolproof
- With client isolation on the guest WiFi, deauth attacks had limited lateral impact
- ESP8266 was still able to broadcast beacon spam, but hardened clients ignored fakes

---

## Hardening Checklist
- [x] Change default SSID and admin password
- [x] Disable WPS
- [x] Enable WPA2/WPA3 encryption
- [x] Isolate guest network from LAN
- [x] Update router firmware
- [x] Test segmentation with virtualized VMs and IoT

---

## Next Steps
- Explore WPA3-only mode
- Perform packet capture during authentication events
- Use nmap & arp-scan to confirm network visibility boundaries
- Begin planning a Honeypot in lab

---

## Notes
This day focuses on **defensive cybersecurity**—mitigating the risks discovered during earlier offensive testing. All changes were made in an isolated lab with controlled test devices. The goal is to apply real-world WiFi hardening practices while continuing to study for **Security+**.
