# Denise Zorro Co-Processor Riser - Semi Tested

This is a Zorro-II riser to fit an PiStorm2K into a Denise (Mini-ITX Amiga) - https://www.enterlogic.se/?page_id=180 
A Zorro-II slot is 98% the same as the A2000 Co-Processor slot in terms of signals however it is buffered. 
This works in Denise as it utilises non-buffered Zorro-II slots so there is no concern over considering extra delay. 

It may however work on other Zorro-II machines but has only been tested on Denise.

Initially designed to use the "A2000" version of the PiStorm2K which re-generates the 7MHz signal from C1/C3 but this did not work (I suspect due to a dodgy chip on my board). 
Running E7MHz from Pin 92 to Pin 7 and it worked. 
It is however still recommended to use the "A2000" version as this adds a header that can be used for other functionality.

See individual README.md in the folder for more details.

### IPL0-2

The A/B2000 utilise IPL0-2 as EINT7, EINT5 & EINT4. These are (justifyably) left off Denise.
To quote Dave Haynie 
>"Only the /INT2 and /INT6 interrupt inputs are actually supported by Commodore-Amiga as part of the Zorro-II specification; the A2000 hardware did not provide the to software the required support mechanisms for the safe use of these lines. 

Unfortunately while justified to leave them off it does mean that things won't work properly. As a result you need either to use link wires under the board to bridge between the processor and the Zorro-II slot or utilise the header included for that purpose on the riser. 

### HDMI

The HDMI out awkwardly *tight* to the Memory if a normal HDMI cable is used. Am angled adaptor is recommended.

### Support

There is no support for the PiStorm2K, it's recommended to firmly attach the Pi to the PiStorm2K and use a spacer on the rear "top" corner to rest against Paula. 

### Bus Arbitration 

This does not do *any* Bus Arbitration. Either special firmware is required or the original 68k needs to be removed. 

### E Clock - Denise Specific

On the A500+ and other later revision Amigas there is a 68R resistor (R109) between the Processor/E (Pin 20) and the Odd/Even CIA chips (Pin 25), E is then connected directly from the CPU to the Edge Slot.
On Denise there is a 68R resistor between the processor and the Zorro-II slot and this is then connected to the Odd/Even CIA chips. 

What this means is how you handle the E-Clock differs if the PiStorm is alone (ie no 68K) or the 68K is still on the board. 

If PiStorm is alone then there is no 68R between it and the Odd/Even CIA and the jumper should be set to "Enable E Clock (+ 68R)".  
If the 68K is still in the socket ***AND*** you have special firmware that disables the E-Clock on the PiStorm then the jumper should be set to "Enable E Clock".

### Special Firmware

I will release the special firmware for PiStorm when it's been further tested! 

#### Swapping between PiStorm and 68k.

Connect Pin 2 of H11 (in between the Zorro slots at the "front") to the header/jumper on PiStorm2K. You can then swap using Num-lock and a reset.

### Version History

v1.0 - Initial design - Built & tested.
V1.1 - Added Zorro-II Pin 92 to Co-Pro Pin 7, adds more text and cleans up a few traces. 
