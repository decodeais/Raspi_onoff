# Raspi_onoff


A simple way to power a Raspberry Pi on or off without data loss. 
Any GPIOs can be used.

![Logo](./images/schematic.png)

The "Run" pin refers to the test pad on the back of the Zero 2W.

The LED is optional but helpful for recognizing the power state (off or on).

Only two small changes are needed in the config.txt:
* Lock the Run/Reset pin while the operating system is running
* Enable shutdown for power-off

Initialization in config.txt in the boot directory:

```
gpio=27=op,dl 
dtoverlay=gpio-shutdown,gpio_pin=17,active_low="y"
```
From the command line:
```shell

sudo sh -c 'echo "gpio=27=op,dl" >> /boot/firmware/config.txt'
sudo sh -c 'echo "dtoverlay=gpio-shutdown,gpio_pin=17,active_low=\"y\"" >> /boot/firmware/config.txt'






