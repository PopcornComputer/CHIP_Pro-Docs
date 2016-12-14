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

TKTK - images showing power connections?

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

Customize the buildroot using 

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

## Use It 

Now that you have power and an operating system, you can connect to your CHIP Pro to test software and hardware, customize it, or load new software. There are two very important connections for this: serial and network. 

### Serial Connection

The most basic connection to CHIP Pro is a serial connection, controlled through a host computer's terminal program.

#### UART

**Materials:**
* USB-UART cable ([for example](https://www.amazon.com/Armorview-PL2303HX-RS232-Module-Converter/dp/B008AGDTA4))
* Drivers
* Soldering gun
* Solder
* Pin headers
* Computer with monitor (for example, a [CHIP](http://www.getchip.com/)!)
* Terminal program for Windows such as [cygwin](https://cygwin.com/) or [PuTTY](http://www.chipkin.com/using-putty-for-serial-com-connections-hyperterminal-replacement/) (OS X and Linux have terminals built-in)

A UART to USB serial connection between CHIP Pro and your computer offers the most comprehensive look at what's happening in CHIP Pro as it boots, since you can get all message output from the moment it starts booting. You'll need a USB to UART cable and the appropriate drivers for your computer's OS. 

For example, [this](https://www.amazon.com/Armorview-PL2303HX-RS232-Module-Converter/dp/B008AGDTA4) cable uses the Prolific hardware, with drivers [available on their site](http://www.prolific.com.tw/US/ShowProduct.aspx?pcid=41&showlevel=0041-0041). Another popular chipset for these cables is FTDI.

Connect the cable to your computer and the UART pins on CHIP-Pro. You'll need to solder some headers onto CHIP-Pro for a reliable connection to the loose wires on the cable. The black cable goes to ground, green is usually RX, and white is usually TX, but there's no guarantee. 

From your computer's terminal, use the command

``` 
screen /dev/tty.usbserial 115200 #OS X
screen /dev/tty.USB0 115200      #Ubuntu
```

Another popular program besides screen is `cu`. 

For Windows read [our guide](http://docs.getchip.com/chip.html#using-putty) on connecting with Putty or cygwin.

#### USB Gadget Serial

**Materials:**
* USB micro-USB A cable ([for example](http://www.cablewholesale.com/products/usb-firewire/usb-2.0-cables/product-10u2-03101bk.php))
* Computer with monitor (for example, a [CHIP](http://www.getchip.com/)!)
* Terminal program for Windows such as [cygwin](https://cygwin.com/) or [PuTTY](http://www.chipkin.com/using-putty-for-serial-com-connections-hyperterminal-replacement/) (OS X and Linux have terminals built-in)

If your OS is configured for gadget serial, this is usually the easiest way to get inside CHIP Pro's software is using USB Gadget serial. While you won't be able to get boot messages, since the serial emulation won't be ready, all you need is a USB micro to USB A cable to connect CHIP Pro to your computer. From your computer's terminal:

```
screen /dev/tty.usbmodem1440 115200 #OS X
screen /dev/tty.ACM0 115200         #Ubuntu
```

Note that for OS X, you either need to list out all the tty devices with `ls /dev/tty.usbm*` to find the actual ID, or use the tab key to autocomplete, like `screen /dev/tty.usbm <tab>`.

For Windows read [our guide](http://docs.getchip.com/chip.html#using-putty) on connecting with Putty or cygwin.

### Log In
Once you have connected via serial, you'll be prompted for a username and password. The defaults are `chip` and `chip`. Change your password with `pwd`.

### Network

Once you have connected to CHIP Pro with a serial connection, you can set it up for network access. How this happens depends on the OS you have loaded onto CHIP Pro. Most likely you'll be able to make basic connections to a WiFi network using either `connman` or `nmcli` in the command line.

#### Connman

The basic commands to connect are done in a connman terminal. You can learn more about connman [here](https://wiki.archlinux.org/index.php/Connman)

```
sudo connmanctl # enter the connman terminal

> enable wifi # turn on wifi
> scan wifi # find networks
> agent on # let connman prompt for a password when needed
> services # list all the visible networks so you can get the wifi_ id string
> connect wifi_7cc70905cd77_4e5443_managed_psk #connman will then prompt for password
> quit # get back to linux terminal
```

If your network doesn't have a password

#### nmcli

You may find `nmcli` is the gateway to your network. There's a lot of information about nmcli on the [archlinux site](https://wiki.archlinux.org/index.php/NetworkManager). If nmcli is what you need, here's the commands you can use to connect to a network using your serial connection in the terminal:

```
sudo nmcli d wifi # list visible wifi networks
sudo nmcli d wifi connect "Network SSID Name" password "Your Password" ifname wlan0 # if network is hidden add this to end: hidden yes
```

#### ping!

It's always reassuring to check that you have a connection with ping:

```
ping 8.8.8.8 #google dns server
```

# Manufacturing with CHIP Pro
If you want to manufacture a product with CHIP Pro here's some advice.
	
# Open Source
The CHIP Pro is open source hardware. Get all the details in our [github repo](https://github.com/NextThingCo/CHIP_Pro-Hardware)