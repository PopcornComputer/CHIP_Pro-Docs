# C.H.I.P. Pro Overview

![C.H.I.P. Pro](images/CHIP-Pro-Side-ISO.png)

The C.H.I.P. Pro System-on-a-Module is designed to get you making great products instead of re-inventing computers. It's a low-cost, high-capability module that lets you focus on fast iterations of brilliant ideas that will be ready to manufacture.

This document provides technical details on the module and basic guides for getting started with working with C.H.I.P. Pro. To get the most out of developing and designing for C.H.I.P. Pro, we recommend the [C.H.I.P. Pro Development Kit](http://docs.getchip.com/chipprodevkit.html).

## Overview

C.H.I.P. Pro is a breadboard-friendly and surface-mount-ready computer designed from the ground up to power the next generation of smart devices.

C.H.I.P. Pro is powered by GR8, a system-in-package (SiP) that was designed by us at Next Thing Co. GR8 features a 1GHz Allwinner R8 ARM Cortex-A8 processor, Mali400 GPU, and 256MB of Nanya DDR3 DRAM. in a 14mm x 14mm FBGA package. C.H.I.P. Pro adds to the GR8 with 512MB of high-speed NAND storage, WiFi and Bluetooth connectivity, power and battery management, pins for popular I/O busses, USB gadget, the verstatility of mainline Linux, all on a compact footprint.

The module offers all the popular interfaces you'd expect. With two UARTs, a Two Wire Interface, a parallel camera interface, SPI, two PWM channels, a USB 2.0 OTG, and a USB 2.0 Host, C.H.I.P. Pro is packed full of opportunity. Comprehensive audio handling includes a built-in 24-bit ADC/DAC for stereo audio in and out, One Wire Audio digital out, and I2S digital audio for interfacing with professional audio DACs.

C.H.I.P Pro is CE, IC, and FCC part 15 modularly certified, making integration into end products easy. The on-board Realtek 8723DS combination module provides compliant Wi-Fi B/G/N and Bluetooth 4.2 Low-Energy connectivity. A software controlled antenna path selects between the on-board chip antenna or a uFL antenna connector where several pre-certified antennas can be added to boost wireless transmit and receive range. 

Charge or power from a battery, use an external power supply, or power it from USB. On-board Power management with the AXP209 provides plenty of power options to better match your applications: mobile, industrial, and low-power are all possible with C.H.I.P. Pro. 

![C.H.I.P. Pro](images/CHIP-Pro-Side-Crop.png)

C.H.I.P. Pro is rated to operate between 2.9V-6V in temperatures ranging between 0 and 70 degrees Celsius and measures 45mm x 30mm.

We can't wait to see how you'll integrate C.H.I.P Pro in to your next product.

## Block Diagram

![C.H.I.P. Pro Block Diagram](images/CHIP-Pro-Block-Diagram.png)

## GR8 SiP

![GR8](images/CHIP-Pro-Exploded-View.png)

C.H.I.P. Pro is built around the GR8 System-in-Package that combines an Allwinner R8 with DDR3 memory on the same piece of silicon. Basic specifications are as follows:
 
* 1GHz Next Thing Co. GR8 ARM Cortex-A8 with ARMv7 instruction set and NEON coprocessor
* Mali-400 GPU supporting OpenGL ES1.1/ 2.0 and OpenVG 1.1
* 256MB DDR3 RAM

More information about the GR8 SiP can be found on the [GR8 documentation page](http://docs.getchip.com/GR8.html) and in the [GR8 data sheet](https://github.com/NextThingCo/CHIP_Pro-Hardware/raw/master/Datasheets/GR8_Datasheet_v1.0.pdf)

# Specifications

## C.H.I.P. Pro Exposed Interfaces

* 1x Two Wire Interface
* 2x UART (1x 2-wire and 1x 4-wire)
* SPI enabling SD card interface 
* 2x PWM
* 6-bit ADC
* I2S Digital Audio
* S/PDIF IEC-60958 Digital Audio Input and Output 
* 2x USB HS/FS/LS
	* USB 2.0 Host
	* USB 2.0 OTG
* Parallel Camera Interface 
* 3.3V DC supply
* 27 GPIO

## Audio

* Stereo analog input 44.1K or 48K sampling rate
* Stereo analog output 44.1K or 48K sampling rate
* Programmable phantom power for mic in
* Bi-directional I2S bus for external DAC codecs

## Power and Battery Management

* AXP209 power management unit, connected to a dedicated I2C bus
* 2.9V to 6V
* 0 to 70 degrees Celsius 

## Wireless Connectivity

* Realtek 8723DS Combination Module
* Bluetooth 4.2 LE
* WiFi 802.11 b/g/n
* uFL antenna connector
* FCC/CE/IC certified

## Operating System

* GadgetOS, a Linux optimized for GR8 and C.H.I.P. Pro
* Debian for C.H.I.P. Pro, for a familiar Linux experience
* Next Thing Co rootfs on GitHub so developers can create their own Linux distro for C.H.I.P. Pro

## Mechanical Drawing

You can download a high resolution version of this image [here](CHIP-Pro-PCB.png)
![Mechanical Drawing](images/CHIP-Pro-PCB_sm.png)

### Dimensions

Refer to the following diagram for the complete dimensions of C.H.I.P. Pro

## PCB Footprint

C.H.I.P. Pro is designed for scale and ready to drop into any SMT manufacturing line. The exterior dimensions for the PCB pads for C.H.I.P. Pro are 32 mm x 47.60 mm (1.26 in x 1.87 in). More detailed dimensions for your board layout are in the following diagram.

![C.H.I.P. Pro PCB Footprint](images/CHIP-Pro-Footprint.png)

## Data Sheet

While this documentation contains much of the needed technical info for C.H.I.P. Pro, the complete data sheet for C.H.I.P. Pro is available [on our C.H.I.P. Pro Hardware github repo](https://github.com/NextThingCo/CHIP_Pro-Hardware/raw/master/Datasheets/CHIP_PRO_Datasheet_v1.0.pdf)