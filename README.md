# neopixel-gui
Simple graphical interface for controlling neopixel RGB LEDs on a Raspberry Pi

## Introduction

This project is currently work in progress. More documentation will be provided in future.

## GUI Layout

The user interface is intentionally basic in appearance using large buttons. This is so that it is suitable for use in a disco environment using a touchscreen (eg. using VNC from a touchscreen laptop).

The Apply button needs to be pressed for the changes to take effect, which allows the user to choose all the appropriate settings prior to applying them.

![NeoPixel GUI screenshot](docs/screenshot-v0-1.png "Screenshot of NeoPixel GUI Version 0.1")



## Supported platform

This is designed to run on a Raspberry Pi and Raspberry Pi 2.
It has been tested with the [MyPifi Neopixel board](http://smstextblog.blogspot.co.uk/2015/03/afirstly-thank-you-for-purchasing-this.html) and by using a simple MOS-FET switch circuit. Using a MOS-FET requires that the LEDinvert be selected.

## Pre-requisites

Install the neopixel library from: https://github.com/jgarff/rpi_ws281x/tree/rpi2

This needs to be installed for python3
The final step should be:
sudo python3 setup.py install

## Install

Download and extract files into a new folder named /home/pi/neopixel
Copy the appropriate desktop and startmenu files as listed in the INSTALL.md guide. Restart the lxpanel and then the icon should appear on the normal start menu.

A more detailed install guide is provided in the file INSTALL.md


## More Information 

More information will be provided on [www.penguintutor.com](http://www.penguintutor.com)


