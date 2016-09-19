contents of the design document

# Intended Purpose / Applications

A description of the various applications.

- Underwater, in a river.
- Monitoring cisterns and similar water storage enclosures.
- Likely attached underwater to various cinder blocks, and the like.
- Needs to be inexpensive, easy for people to use, try to use locally-available materials for enclosure so that fixes are easy.

Implications for battery life, enclosure, accessibility.

[graphic of various applications]

https://publiclab.org/notes/kinasmith/06-14-2016/fixed-riffle-sd-card-power-consumption

0.5mA
The Riffle sleeping consumes about 300µA, and the SD card consumes about 200µA.

Arduino Uno is 45 mA

Arduino Pro Mini w/ LED smashed: http://www.home-automation-community.com/arduino-low-power-how-to-run-atmega328p-for-a-year-on-coin-cell-battery/ gets 0.05 mA

2000 mAh battery

| device | mAh | hours | days | 
| -------------:  | -------------: | -------------: |
| Arduino UNO | 50 | 40  | 1.7 |
| Riffle_328 | 0.5  | 4000  | 167 |
| Arduino Pro Mini (modified) | 0.05 | 40000 | 1667 |


# Enclosure designs

### PVC

pros: ubiquitous materials, intended for waterproofing
cons: actually difficult to make seal and then to reopen

### Bottle

pros: ubiquitous, very cheap
cons: plastic not great for working with -- solution is rubber stopper

### Board shape 

Thin enough to sit inside bottle.
Bottle means that pins and buses need to be oriented at end of board. 
This also works for PVC.

# Power / battery life

lipo charging
diode drop
mosfet on breakout
mosfets for sd card
mosfet for battery monitor circuitry

[comparison with current power usage of riffle vs. uno]

# Sensors / Modularity

### Protoboard

### Instrument design

Reference to the other instrument designs

# Storage / Data retrieval

### eeprom
### sdcard
### audio 
### USB

# Pins and Bus interfaces

### analog and digital pins
### i2c
### spi
### rx / tx on baord itself

# Iteration Workflow on Github

idea:  ea. of the repos has the hardware and software necessary to move forward
try to make the modules s.t. they can be used on other circuits too -- include some more general code 
use issues in each repo -- *not* preserved -- this is where publiclab wiki structure can be very helpful
write up some description of the ecosystem


