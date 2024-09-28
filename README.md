# Hot Plug Wifi Adapters for OpenIPC Radxa GroundStation (PixelPilot_rk)

## Description
Configure the `autoload-wfb-nics.sh` script in your Radxa GroundStation to enable the support for hot plugging Wifi Adapters.

## Features
- Hot plug wfb-ng supported wireless NICs
- Wifibroadcast will automatically be restarted with the currently plugged in adapters
- No system reboot required
- No configuration changes for wfb-ng required


## Installation

- Execute the following commands one-by-one to move the scripts from hot-plug-wfb-nics folder to correct locations:
  - `cd /home/radxa/hot-plug-wfb-nics`
  - `sudo chmod +x autoload-wfb-nics.sh`
  - `sudo cp autoload-wfb-nics.sh /config/scripts/`
  - `sudo cp init-nics.service /etc/systemd/system/`
  - `sudo systemctl enable init-nics.service`
  - `sudo cp 98-custom-wifi.rules /etc/udev/rules.d/`
- Reboot the radxa

## Usage
- Once installed, you can plug or remove wifi adapters into the ground station and it will automatically detect and restart wifibroadcast with the correct adapters
- Internal Wifi adapter should work normally and you should be able to connect to your network using it
 
