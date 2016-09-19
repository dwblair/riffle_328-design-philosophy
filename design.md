contents of the design document

# Motivation / Applications

A description of the various applications.

- Underwater, in a river.
- Monitoring cisterns and similar water storage enclosures.
- Likely attached underwater to various cinder blocks, and the like.
- Needs to be inexpensive, easy for people to use, try to use locally-available materials for enclosure so that fixes are easy.

Implications for battery life, enclosure, accessibility.

<img src="pics/riffle-applications.png" width=300>
<img src="pics/river_app.jpg" width=300>
<img src="pics/hobo_depth.jpg" width=300>
<img src="pics/hobo_conduct.jpg" width=300>

Proprietary dongles 

<img src="pics/hobo_dongles.jpg" width=300>

# Enclosure designs

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

#### Cap
<img src="pics/screws_a.jpg" width=300>
<img src="pics/screws_b.jpg" width=300>

### Other

<img src="pics/compost.jpg" width=300>
<img src="pics/riffle_campout.jpg" width=300>
<img src="pics/riffle_campout_2.jpg" width=300>
<img src="pics/riffle_3d_a.png" width=300>
<img src="pics/riffle_3d_b.png" width=300>
<img src="pics/riffle_3d_c.png" width=300>
<img src="pics/riffle_3d_d.png" width=300>
<img src="pics/riffle_3d_e.png" width=300>

### Board shape 



<img src="pics/riffle_orig_front.png" width=300>
<img src="pics/riffle-ito.jpg" width=300>
<img src="pics/ftdi.jpg" width=300>

<img src="pics/riffle_orig_nice.jpg" width=300>

<img src="pics/riffle_frozen.jpg" width=300>

Thin enough to sit inside bottle.
Bottle means that pins and buses need to be oriented at end of board. 
This also works for PVC.

# Power / battery life

lipo charging
diode drop
mosfet on breakout
mosfets for sd card
mosfet for battery monitor circuitry

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

<img src="pics/sniffle.jpg" width=300>
<img src="pics/coqui_audio.jpg" width=300>

### Instrument design

Reference to the other instrument designs

# Storage / Data retrieval

### eeprom
### sdcard
### audio 
### USB

# Pins and Bus interfaces

[ PIC of READOUT on BACK of BOARD]
[ PIC of EAGLE SCHEMATIC ] 

### analog and digital pins
### i2c
### spi
### rx / tx on baord itself

# Iteration Workflow on Github

[ GRAPH ] 

idea:  ea. of the repos has the hardware and software necessary to move forward
try to make the modules s.t. they can be used on other circuits too -- include some more general code 
use issues in each repo -- *not* preserved -- this is where publiclab wiki structure can be very helpful
write up some description of the ecosystem


