# neopixel-gui install guide

Guide to installing the neopixel gui application.

## Hardware requirements

*WARNING: Read carefully before connecting Neopixels to your Raspberry Pi*

The neopixel gui application is designed for use with a Raspberry Pi. It controls a strip of RGB LEDs with integrated controller IC such as WS2811 or WS2812. Adafruit products are named Neopixels, but other suppliers may refer to these as RGB LEDs, WS2811, WS2812 or WS281x LEDs.

It should work with all current versions of the Raspberry Pi. If using a Raspberry Pi 2 then it is important that the neopixel library is installed from the link provided in this guide earlier versions of the library do not work with the Raspberry Pi 2.

Using the neopixel libarary the neopixels can be driven from the Raspberry Pi GPIO connector. It needs to use PWM which is available on *GPIO pin 18* (physically pin 12 on the board).

The GPIO port works at 3.3V, but Neopixels require a 5v power supply and 5v signal. This can be done using a voltage level shifter circuit.

I used a [MyPifi Neopixel board](http://smstextblog.blogspot.co.uk/2015/03/afirstly-thank-you-for-purchasing-this.html) for testing the software.

## Raspberry Pi with Raspbian

These instructions are based on Raspbian provided with NOOBS version 1.4. It should work with any recent version of Raspbian. 

[Download the latest version of NOOBS](https://www.raspberrypi.org/downloads/)

## Pre-requisites

The software is written for Python version 3 and needs the NeoPixel library to be installed for Python 3. To work with Raspberry Pi then the updated version needs to be installed (this can be installed on the older Raspberry Pi as well).

First install the developer libraries using
`sudo apt-get install build-essential python-dev python3-dev git scons swig`

(this includes the Python 2 developer libraries which are not required but are useful to install anyway)

Download the neopixel code from github
`git clone https://github.com/richardghirst/rpi_ws281x.git`

```bash
cd rpi_ws281x
scons
```

Change to the python directory 
```bash
cd python
```

Install the Python 3 library file using

```bash
sudo python3 setup.py install
```

If you also want to use the library with Python 2 you can also install using

```bash
sudo python setup.py install
```
(this last step is not required for this software, but may be useful if you install any other Neopixel software that uses Python version 2).


## Install the Neopixel GUI software

Install the software from git using 

```bash
git clone https://github.com/penguintutor/neopixel-gui.git neopixel
```

you can now run the command using

```bash 
cd neopixel
gksudo python3 rpnpg.py
```

To add to a new DJ Start Menu use:
```bash
cd ~/neopixel
mkdir -p ~/.config/menus
cp lxde-pi-applications.menu ~/.config/menus/
mkdir -p ~/.local/share/desktop-directories
cp dj_menu.directory ~/.local/share/desktop-directories/
mkdir -p ~/.local/share/pixmaps
cp headphones.png ~/.local/share/pixmaps/
cp rpnpgpicon.png ~/.local/share/pixmaps/
mkdir -p ~/.local/share/applications/
cp rpnpgp.desktop ~/.local/share/applications/
lxpanelctl restart
```

## gksudo warning message

When first running you will get a warning message that the application is running with super user privileges without asking for a password. "Granted permission without asking for password". This is required to be able to access the GPIO ports on the Raspberry Pi. If you tick the "Do not display this message again" box then you will not be warned of this again in future.

## Initial configuration

Once the application is running choose the Config option to set the number of LEDs in your Neopixel LED strip. You will then need to close and restart the application for the changes to take effect.



