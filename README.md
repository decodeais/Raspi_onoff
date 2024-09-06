# Raspberry Pi GPIO Safe Shutdown and Wakeup Solution

## Overview
This project provides a simple and reliable way to safely turn your Raspberry Pi on and off using GPIO pins, preventing data corruption and ensuring safe operation. It's compatible with any Raspberry Pi model, including the Raspberry Pi Zero 2W.

![Safe Shutdown Schematic](./images/Schematic.png)

## Key Features
- Safe shutdown using GPIO pins.
- Optional LED indicator for power status.
- Prevents data loss and system corruption.
- Works with any GPIO pins on the Raspberry Pi.

## Installation
Follow these steps to modify the `config.txt` for safe shutdown:

1. Open the `config.txt` file located in `/boot/`.
2. Add the following lines:
   ```bash
   gpio=27=op,dl
   dtoverlay=gpio-shutdown,gpio_pin=17,active_low="y"


From the command line:
```shell

sudo sh -c 'echo "gpio=27=op,dl" >> /boot/firmware/config.txt'
sudo sh -c 'echo "dtoverlay=gpio-shutdown,gpio_pin=17,active_low=\"y\"" >> /boot/firmware/config.txt'






