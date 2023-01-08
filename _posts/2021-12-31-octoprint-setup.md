---
title: Install Octoprint (Draft) 
date: 2021-12-31 12:00:00 -500
categories: [tutorial,software,microelectronics]
tags: [ender 3,octoprint,3D print,install,software]
---

1. Download and install Balena Etcher: <https://www.balena.io/etcher/>
2. Download Octoprint: <https://octoprint.org/download/>
3. Extract Octoprint
4. Insert a microsd card and adapter into your computer
5. Open Balena etcher and flash `Octpi.img` file to microsd card
6. Download Sublime: <https://www.sublimetext.com/>
7. Open `octopi-wpa-supplicant.txt` in sublime text editor
    - uncomment the country you're in
    - uncomment network and put in wifi SSID and Password in quotes
    - save txt file
8. Put in microsd card in Raspberry Pi
9. Take a microusb cable and plug one end into the Ender 3 and the other into the raspberry pi
10. In the other USB port, plug your webcam into it
11. Add a microusb power supply and plug into power port in raspberry pi