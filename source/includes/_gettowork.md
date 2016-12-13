# Get Working With CHIP Pro

## Power In, Power Out

CHIP Pro can be powered in a few ways, all managed by the AXP209 power management circuit. For simple applications on the test desk, power can be provided over the micro USB cable from a power supply or powered USB hub. But CHIP is for building, and depending on the nature of your product, there are different power options to make it easier to make with CHIP Pro.

* CHGIN - connect 4.8 to 6 V of power to pin 4 (and GND) to provide power to CHIP Pro. If you have a 3.7V Lithium Polymer (LiPo) battery connected to BAT, then power provided to CHGIN will also charge the battery.
* BAT - connect a 3.7V Lithium Polymer (LiPo) battery to pin 8 (and GND) to provide power to CHIP Pro. You can charge the battery by providing voltage to the CHGIN pin.
* VBUS - connect 5 V to pin 50 (and GND to pin 53) to provide power to CHIP. 

CHIP Pro has a couple options for providing power to peripherals and sensors.

* VCC-3V3 - pin 2 provides 3.3 V for sensors and anything else. This pin can provide a maximum of TKTK amps.
* IPSOUT - pin 3 provides a software defined voltage at TKTK amps for powering peripherals.
* USB Host - provide power to USB peripherals
* PWRON - connect to ground to turn CHIP Pro on and boot the operating system.

## Get an Operating System

Like it's larger brother CHIP, CHIP Pro's GR8 SiP can run mainline Linux. This provides security, flexibility, robust tools, and open-source options for getting your product working. However, in the interest of power consumption and storage space, we have several options to best fit your production.

### Gadget OS - easy to run

---GADGET--- TKTK

###	Buildroot - Minimal and Fast

Buildroot is a tool for building and cross-compiling a linux distribution that only has what you need. Setting up buildroot requires either a [virtual machine](http://docs.getchip.com/chip.html#installing-c-h-i-p-sdk) or a computer running Ubuntu OS, [setup for flashing](http://docs.getchip.com/chip.html#setup-ubuntu-for-flashing).

### Things you will need

 * C.H.I.P. Pro
 * Standard-USB to micro-USB connector
 * An appendage to hold down the FEL button
 * Separate computer with the CHIP SKD [virtual machine](http://docs.getchip.com/chip.html#installing-c-h-i-p-sdk) or Ubuntu OS, [setup for flashing](http://docs.getchip.com/chip.html#setup-ubuntu-for-flashing).
 * Separate computer with [Chrome](https://www.google.com/chrome/browser/desktop/index.html) or [Chromium](https://www.chromium.org/getting-involved/download-chromium) browser 

#### Modify and Build
[CHIP-buildroot](https://github.com/NextThingCo/CHIP-buildroot) is used to build buildroot and the linux kernel. Its Makefile operates on a `.config` file which specifies options to include in the build. The `.config` lives in the repository's root, whereas the one for the linux kernel is: ./board/chip/linux.config/

First, clone the buildroot repot and create the default config file with:

```
git clone https://github.com/NextThingCo/CHIP-buildroot
cd CHIP-buildroot
make chippro_defconfig
```

This will copy the the `chippro_defconfig` file as `.config` in the root of the repository. Other default config targets for other hardware can be found in the `config` subdirectory. You can, of course, create your own config files and use them later.

Customized the buildroot with using 

```
make nconfig
```

For Linux (which will modify the linux.config under board/nextthing/chip/): 

```
make linux nconfig
```

Now

```
make
```

from the buildroot repository root. This will cross-compile linux/buildroot for CHIP Pro. The targets wind up in the ./output/images directory. If you make changes to your config files, you can just `make` again without a `make clean`. 

#### Flash

TKTK

### Debian - Familiar and Strong
If you need to, you can run a standard Debian distribution, complete with all the package managers and conveniences you know and love. While this is great for development, it may not be optimal to deliver your product with a full debian installation. 

### Things you will need

 * C.H.I.P. Pro
 * Standard-USB to micro-USB connector
 * An appendage to hold down the FEL button
 * Separate computer with [Chrome](https://www.google.com/chrome/browser/desktop/index.html) or [Chromium](https://www.chromium.org/getting-involved/download-chromium) browser

#### Flash

Visit our OS flash site at [flash.getchip.com](http://flash.getchip.com) in Chrome or Chromium browser. Hold down the FEL button on CHIP Pro and follow all the instructions in the browser. 

### Use NTC rootfs to make your own distro

For those who have their own Linux distribution or want to make their own, we provide our rootfs [on github](http://github.com/NextThingCo/TKTK). This provides the CHIP Pro-specific software that can be used to pair with a custom kernel and needed binaries. 



