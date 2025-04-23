# Day 1 - Deauthentication Attack Basics
## Date:
April 22, 2025

## Goal:
Test basic deauthentication attacks using ESP8266 Deauther firmware in an isolated network.

## Tools & Setup:
- ESP8266 Deauther (version 3.0.5)
- Test network: Cyber-Lab (Guest Network)
- Devices: iPhone 12 Pro Max, Kali Linux VM, 2021 MacBook Pro
- Firmware settings: default packet rate, 80% power.

## Actions Taken:
1. Flashed firmware and connected to `pwned` AP
2. Opened web interface via `192.168.4.1`
3. Scanned for nearby APs and clients (30 total AP's)
4. Selected `CyberLab-Guest` and performed deauth attack on my phone
5. Observed device behavior and re-authentication process

## Observations:
- Phone disconnected instantly, auto-reconnected after ~10 seconds
- VM was not affected (possibly because it was not using the same adapter)
- Deauth packets were visible in Wireshark when mirrored via router

## Takeaways:
- Deauth attacks work on most unprotected Wi-Fi clients
- Isolation from main network worked perfectly — no unintended disruption
- Will explore `attack -> beacon` mode next


## Next Steps:
- Try beacon spam
- Verify MAC randomization behavior of test devices
- Add screenshots to `screenshots/` folder

See Day 2 Notes...

With love, intended for educational purposes only... 