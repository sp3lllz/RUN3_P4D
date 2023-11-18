# RUN3_P4D
The game controller for keyboard sickos

# Getting Started

## Fully assembled kits
If you have purchased a fully assembled version from me there should be no setup needed. It should be configured to the console you requested (Switch, PS4 or XImput for PC) ready for plug and play use!

## DIY Kits

### Required items

The Maca controller PCB varient of your choice and a compatible Microcontroller board 

#### Compatible RP2040 Controllers

For the Main version of the board designed for the Official Pi Pico the following versions are compatible:

- Rasberry Pi Pico
- Rasberry Pi Pico W
- Pimoroni Pico LiPo
- Waveshare RP2040-Plus

I would recomend for ease of soldering to get a version with pre soldered legs, If you would like native USB C I would recomend the Waveshare or the Pimoroni board as the Office Pi Pico is Micro USB 

For the RP2040-Zero version only the Waveshare RP240-Zero is compatible due to its more compact layout.

Addtionally you will need 18 Mechanical keyboard switches and keycaps of your choice. 

A PC or Mac with an internet connection. 

[Flash_Nuke.uf2](https://github.com/dwelch67/raspberrypi-pico/raw/main/flash_nuke.uf2)

[GP2040-CE for your board version](https://gp2040-ce.info/downloads/download-page/)

You will also need a soldering iron and some solder and some basic soldering skills. 

### Assembly

First step is to solder the RP2040 Controller of your choice to the Main PCB for the Pi Pico or its clones this is relativly simple as it's a through hole situation, if you got a version without pre soldered legs I recommend that you solder the legs to the Pico board first then slot the legs through the pcb placing the Pico on the top side of the board and soldering it from underneath the RP2040-Zero version is a little more challenging as its pad based soldering. A good tip is to place the board on pcb with the USB C port facing up and start with solding two opposite corners after squaring it up on the board. Once the corners are tacked down the board should stay in place and you can go round and solder each pin more easily. 

Next up is time to do the switches. you can do these in any order these again are through hole so fairly easy to solder down. I would reccomend that you get 3 pin switches as these hold more stable and square while soldering them down. 

### Software Setup

For the software we are using the GP2040-CE project. 

First off download the `flash_nuke.uf2` file from the [pi foundation github](https://github.com/dwelch67/raspberrypi-pico/raw/main/flash_nuke.uf2) to clear any exsisting firmware from your controller. 

> [!CAUTION]
> Make sure you have retrived any files from the pico if you have used this for a previous use as it will be wiped when you do this. 

with the Pico unplugged press and hold the button labeld `BOOTSEL` on the RPI and Pimironi or `BOOT` on the Waveshare boards while plugging in the controller to your Mac or PC within a few seconds a file window should show up on your computer drag the `flash_nuke.uf2` file into the window and then the window should dissapear within a few seconds. Once the pico has rebooted it will bring back up the file window now [download the correct version of the GP2040-CE firmware ](https://gp2040-ce.info/downloads/download-page/) for the Pi Pico Pimirioni and Wave Share use the Pi Pico for the Pi Pico W use the Pico W firmware, now do the same with this simply drag it to the file window and it will dissapear after a few seconds. 

The pico should then flash the firmeware to itself and reboot within about 60 seconds at most. wait until you hear the windows device connected sound again to know when the controller has rebooted and finished the set up. To confirm the firmware flashed correctly hold down the `SELECT` Button on the controller while replugging the controller into the PC then in your browser navigate to http://192.168.7.1/ you should be presented with an info page for the microcontroller that looks somthing like this 

> System Stats
Version
> Pico-W (GP2040-CE_0.7.5_PicoW.uf2)
>Current: v0.7.5
> Latest:
Memory (KB)
> Flash: 807.07 / 2048 (39.41%)
> Heap: 24.32 / 153.37 (15.85%)
> Static Allocations: 110.63

This means your device flashed correctly. My PCB follows the standard Wiring scheme from the [GP2040-CE FAQ](https://gp2040-ce.info/controller-build/wiring/) so the only thing that you should need to change is in the `Settings` Tab which is to set the Controller to operate in the correct mode you would need eg Nintendo, PS4 or XIMput hit save then youre done and your ready to plug it into your console of choice and start playing! 

