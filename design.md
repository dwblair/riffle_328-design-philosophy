

# Motivation / Background

The initial concept for the Riffle was driven by conversations with Mark Green, a Professor at Plymouth State, about the current technologies used for water monitoring. 

**Proprietary data chain.**  One of the key issues with current water monitoring technologies is that they are typically designed to record data in a proprietary, encrypted format;  the physical hardware almost always requires a special 'dongle' for conveying the data to a PC for analysis and storage; and finally, the software required to decrypt the data is typically expensive, and closed-source, meaning that user modifications or extensions are impossible.  

https://publiclab.org/notes/cfastie/07-20-2014/can-open-source-beat-this
http://www.forestry-suppliers.com/product_pages/Products.asp?mi=84781

- HOBO datalogger used widely; YSI

<img src="pics/riffle-applications.png" width=300>
<img src="pics/river_app.jpg" width=300>
<img src="pics/hobo_depth.jpg" width=300>
<img src="pics/hobo_conduct.jpg" width=300>

Proprietary dongles 

<img src="pics/hobo_dongles.jpg" width=300>



# Project Goals 

A description of the various applications.

- Underwater, in a river.
- Monitoring cisterns and similar water storage enclosures.
- Likely attached underwater to various cinder blocks, and the like.
- Needs to be inexpensive, easy for people to use, try to use locally-available materials for enclosure so that fixes are easy.

Implications for battery life, enclosure, accessibility.

After extensive discussions with Mark, Mary Martin, Patrick Herron, and several others in the community, we decided to focus our project around some particular design goals:

**Developing an open hardware alternative.**  We hoped to leverage the world of open source hardware electronics, and see if we could build a basic water monitor device that allowed for easy hardware modification and reprogramming, and easy for people to add new sensors.  

**Open and accessible data formats.** We also planned to design the device so that it could output data in a common data format (CSV), using accessible data storage media (SD cards).  

**Accessible enclosure materials.** We wanted to use accessible, inexpensive materials in the enclsoure design, to make it easy for people to make repairs, custom modifications, using locally-avaiable materials.  

**Establishing a community of users.** Our hope, too, was to establish a community around such a device, so that hardware users could support one another's efforts, help debug code, and share new designs.  

# Enclosure

### PVC

<img src="pics/pvc_enclosure.png" width=300>
<img src="pics/mchck_oblique.jpg" width=300>
<img src="pics/piglet.png" width=300>
<img src="pics/piglet_cap.jpg" width=300>
<img src="pics/piglet_cap_a.jpg" width=300>
<img src="pics/piglet_adhesive.png" width=300>
<img src="pics/ben_laura.png" width=300>


pros: ubiquitous materials, intended for waterproofing
cons: actually difficult to make seal and then to reopen

### Bottle

<img src="pics/bottle_enclosure.png" height=500>
<img src="pics/riffle-ito-parts.png" height=500>
<img src="pics/riffle-ito-audio.png" height=500>
<img src="pics/rice.jpg" height=500>
<img src="pics/rubber_stopper.jpg" height=300>
pros: ubiquitous, very cheap
cons: plastic not great for working with -- solution is rubber stopper

https://publiclab.org/notes/mathew/02-26-2015/sensors-in-soda-bottles
https://publiclab.org/notes/mathew/01-16-2015/sketching-a-waterproof-pop-bottle-sensor-system


#### Cap
<img src="pics/screws_a.jpg" width=300>
<img src="pics/screws_b.jpg" width=300>

### Other

<img src="pics/compost.jpg" width=300>
<img src="pics/riffle_campout.jpg" width=300>
<img src="pics/riffle_campout_2.jpg" width=300>
<img src="pics/riffle_3d_b.png" width=300>
<img src="pics/riffle_3d_d.png" width=300>

# Board design 

- Atmel vs ARM
- CH340 -- cheap and easy (but not easy to source)
- DS3231 -- want temp-compensated RTC to line up timestamps
- 2x7 header at end -- to allow water bottle config
- SPI and I2C breakouts at end 
- Hardware interrupts D2 and D3 for any related applications (freq-based measurements like conductivity and depth)
- EEPROM for storing configurations
- Mounting holes for gen purpose mounting
- Show highlights / pics

https://github.com/bgamari/riffle
https://github.com/bgamari/riffle/blob/fab/hardware/front.png
https://mchck.org/

<img src="pics/mchck.jpg" width=300>


<img src="pics/riffle_orig_front.png" width=300>
<img src="pics/riffle-ito.jpg" width=300>
<img src="pics/ftdi.jpg" width=300>

<img src="pics/riffle_orig_nice.jpg" width=300>

<img src="pics/riffle_frozen.jpg" width=300>

Thin enough to sit inside bottle.
Bottle means that pins and buses need to be oriented at end of board. 
This also works for PVC.

# Power / battery life

- Battery charging circuit
- But requires protective diode to allow for disconnect from USB Serial chip
- So, want to avoid voltage drop
- So, create “gen” battery input, without diode / voltage drop
- RTC alarm functionality 
- Want very low power -- mosfet on external board, mosfet on SD card, mosfet on battery measurement

lipo charging
diode drop
mosfet on breakout
mosfets for sd card
mosfet for battery monitor circuitry
<img src="pics/sd_card_power.png" width=300>

<img src="pics/lithium_cylinder.jpg" width=300>
<img src="pics/sleep.png">

https://publiclab.org/notes/kinasmith/06-14-2016/fixed-riffle-sd-card-power-consumption

0.5mA
The Riffle sleeping consumes about 300µA, and the SD card consumes about 200µA.

Arduino Uno is 45 mA

Arduino Pro Mini w/ LED smashed: http://www.home-automation-community.com/arduino-low-power-how-to-run-atmega328p-for-a-year-on-coin-cell-battery/ gets 0.05 mA


Problems with SD cards: https://edwardmallon.wordpress.com/2014/09/22/high-sleep-current-problem-solved/

Feather can't mitigate against bad SD card


# Sensors / Modularity



### Protoboard

[NEED PHOTO OF RIFFLE CONNECTING TO PROTOBOARD]
[ALSO OF COQUI ET AL]

https://github.com/OpenWaterProject/riffle_328-proto

<img src="pics/protoboards.png" width=300>
<img src="pics/sniffle.jpg" width=300>
<img src="pics/coqui_audio.jpg" width=300>

### Instrument design

Reference to the other instrument designs

Listing of the repos

- [Openwaterproject](https://github.com/OpenWaterProject) -- the main organization on github
- [riffle_328](https://github.com/OpenWaterProject/riffle_328) -- hardware designs, instructions and software for getting started with the Riffle_328 datalogger
- [riffle_328-conductivity](https://github.com/OpenWaterProject/riffle_328-conductivity) -- Design considerations around conductivity
- [riffle_328-depth](https://github.com/OpenWaterProject/riffle_328-depth) -- Depth measurement circuit prototype
- [riffle_328-turbidity](https://github.com/OpenWaterProject/riffle_328-depth) -- Turbidity sensor prototype
- [riffle_328-thermistor](https://github.com/OpenWaterProject/riffle_328-thermistor) -- Connecting a thermistor to a Riffle
- [riffle_328-i2c](https://github.com/OpenWaterProject/rriffle_328-depth) -- Connecting i2c sensors to a Riffle
- [riffle_328-one-wire](https://github.com/OpenWaterProject/rriffle_328-one-wire) -- Connecting one-wire sensors to a Riffle


# Storage / Data retrieval

### eeprom
- pros / cons
- power consumption

### sdcard
- ed mallon
- power issues

### audio
- webjack

### low-power radio (SPI)
- lora
- rfm60
- nordic

### cell phone
- colombia and john keefe
 

https://publiclab.org/notes/donblair/09-10-2014/water-quality-coqui-voicemails

[PIC OF WEBJACK]



### USB

# Pins and Bus interfaces

<img src="pics/riffle_pinout.png" width=300>
<img src="pics/pinout_schem.png" width=300>

[ PIC of READOUT on BACK of BOARD]
[ PIC of EAGLE SCHEMATIC ] 

### analog and digital pins
### i2c
### spi
### rx / tx on baord itself

[PIC OF RX/TX ON BACK OF BOARD]

# Iterative Development on Github

[ GRAPH ] 

idea:  ea. of the repos has the hardware and software necessary to move forward
try to make the modules s.t. they can be used on other circuits too -- include some more general code 
use issues in each repo -- *not* preserved -- this is where publiclab wiki structure can be very helpful
write up some description of the ecosystem

- issues

# Similar Projects / Future Directions

Mayfly
Feather
Kina's wireless work




