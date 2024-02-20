# AmigaHardware
Random Amiga Hardware. Some development, some practical

# PiStormInside v1.0 - UNTESTED

Edge slot adaptor to fit an A2000/B2000 Co-Processor card inside the A500 case. Designed to fit PiStorm2k internally but other Co-Processor cards *MAY* fit. 
This does not perform *ANY* Bus Arbitration. If you are not running suitable firmware you will need to remove the existing Processor. 

It is designed to fit entirely between the shield and the casing with the Raspberry Pi soldered to the PiStorm2K. If the Pi is fitted to the header then the shield will need to be removed. 
An appropriate brace is required to support the card (I will design one and upload it here once the prototype arrives).

All pins direct connected with the exception of 9,11,12 & 20.   
9, 11 & 20 contain signals that do not exist on the A500.   
12 is CFGIN which on the A500 is connected directly to ground so to save an extra trace the Co-Processor slot merely connects this also to ground.  

* Rev 3 Requires A2000 version of PiStorm2K as there is no 7MHz on pin 7
* Rev 5 Requires A2000 version of PiStorm2K as there is no 7MHz on pin 7
* Rev6A suggest Bridge JP6 to bring 7MHz to pin 7. Can use PiStorm2K either A2000 or B2000 version.
* Rev8A No mods required. Can use PiStorm2K either A2000 or B2000 version.

Designed as a 4-layer with Ground and (+5V) Power planes however can be made as a 2-layer board. 
