# C.H.I.P. Pro Overview


![C.H.I.P. Pro](images/CHIP-Pro-Side-ISO.png)

C.H.I.P. Pro is a system-on-module (SoM) that has 512MB of high-speed NAND storage flashed with our GadgetOS. It can be powered by USB or battery, intelligently managed by the AXP209 power management unit.


C.H.I.P. Pro is powered by GR8, a system-in-package (SiP) that was designed by us. GR8 features a 1GHz Allwinner R8 ARM Cortex-A8 processor, Mali400 GPU, and 256MB of Nanya DDR3 DRAM. in a 14mm x 14mm FBGA package. 

The module offers all the popular interfaces you'd expect. With two UARTs, a Two Wire Interface, a parallel camera interface, SPI, two PWM channels, a USB 2.0 OTG, and a USB 2.0 Host, C.H.I.P. Pro is packed full of I/O expandability. Comprehensive audio handling includes a built-in 24-bit ADC/DAC for analog audio, One Wire Audio digital out, and I2S digital audio for interfacing with professional audio codecs.

C.H.I.P Pro is CE, IC, and FCC part 15 modularly certified, making integration into end products easy. The on-board Realtek 8723DS combination module provides compliant Wi-Fi B/G/N and Bluetooth 4.2 Low-Energy connectivity. A software controlled antenna path selects between the on-board chip antenna or a uFL antenna connector where several pre-certified antennas can be added to boost wireless transmit and receive range. 

![C.H.I.P. Pro](images/CHIP-Pro-Side-Crop.png)

C.H.I.P. Pro is rated to operate between 2.9V-6V in temperatures ranging between 0 and 70 degrees Celsius and measures 45mm x 30mm.

We can't wait to see how you'll integrate C.H.I.P Pro in to your next product.

##Block Diagram

![C.H.I.P. Pro Block Diagram](images/CHIP-Pro-Block-Diagram.png)

##SiP

![GR8](images/GR8-Crop.png)

* 1GHz Next Thing Co. GR8 ARM Cortex-A8 with ARMv7 instruction set and NEON coprocessor
* Mali-400 GPU supporting OpenGL ES1.1/ 2.0 and OpenVG 1.1
* 256MB DDR3 RAM


##Interfaces

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

##Audio

* Stereo analog input 44.1K or 48K sampling rate
* Stereo analog output 44.1K or 48K sampling rate
* Programmable phantom power for mic in
* Bi-directional I2S bus for external DAC modules

##Power and Battery Management

* AXP209 PMU connected to a dedicated I2C bus

##Wireless Connectivity

* Realtek 8723DS Combination Module
* Bluetooth 4.0 LE
* WiFi 802.11 b/g/n
* uFL antenna connector
* FCC/CE/IC certified

##Operating System

* GadgetOS, an Linux optimized for GR8 and C.H.I.P. Pro

##Electrical Characteristics

* 2.9V to 4.3V 
* -25 to 85 degrees Celsius 


##Package Specifications

![Mechanical Drawing](images/CHIP-Pro-PCB.png)

* 45mm x 30mm board
* 38.1mm x 24mm SMT or through-hole
