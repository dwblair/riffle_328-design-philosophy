# Riffle -- Design Philosophy

<img src="pics/riffle_frozen.jpg" width=300> 

https://github.com/bgamari/riffle
https://github.com/bgamari/riffle/blob/fab/hardware/front.png
<img src="pics/riffle_orig_front.png" width=300> 
<a href="pics/riffle_orig_schematics.pdf">riffle_original_schematics</a>

# Motivation

- Water monitoring is very important
- Currently, good solutions exist -- conductivity, temperature, depth
- NIST, rugged, reliable

But:
- Proprietary data format means data is hard to share
- Dongles and licenses increase cost and fragility (high school teacher left system)
- New sensors are becoming available and can be prototyped
- Arduino is inspiring as open source community -- innovating, sharing
- Can we develop a system for getting datalogger electronics into the field easily, and interfacing with new electronics?
- Can we use more accessilbe materials so that more people can be involved?

# Overall summary

- design philosophy

the sd card -- data
protoboard -- folks can prototype their own versions of the board
rechargeable battery -- easy for folks to reuse batteries
other battery port -- avoid the diode
eeprom -- store setting
precision RTC -- needed for environmental measurements
mosfets -- to make it low power
battery level , 3.3v


# Problem definition

https://publiclab.org/notes/cfastie/07-20-2014/can-open-source-beat-this
http://www.forestry-suppliers.com/product_pages/Products.asp?mi=84781

- HOBO datalogger used widely; YSI
- Costs
- Want something extensible
- Something that can connect to the hobby electronics movement
- Use existing code with minimal fuss / muss
- Wanted to make it easy to deploy -- pvc, water bottle, some easy and cheap enclosure
- Easy to share data -- sd card

<img src="pics/hobot_conduct.png" width=300>
<img src="pics/hobot_depth.png" width=300>
<img src="pics/hobot_dongles.png" width=300>
<img src="pics/hobot_pendant.png" width=300>

# Form factor and enclosure
- Wanted to enable water bottle as ‘easiest option’
- Also allows for thin PVC
- the bottle -- deployment, 'detrivore' philosophy

<img src="pics/piglet_adhesive.png" width=300>

<img src="pics/piglet_cap_a.jpg" width=300>

<img src="pics/piglet_cap.jpg" width=300>


<img src="pics/piglet.png" width=300>

<img src="pics/mchck_radio.jpg" width=300>

<img src="pics/riffle_orig_front.png" width=300>

<img src="pics/mchck_oblique.jpg" width=300>

<img src="pics/ben_laura.png" width=300>



https://publiclab.org/notes/mathew/02-26-2015/sensors-in-soda-bottles
https://publiclab.org/notes/mathew/01-16-2015/sketching-a-waterproof-pop-bottle-sensor-system


<img src="pics/bottle_enclosure.png" width=300>

<img src="pics/rice.jpg" width=300> 

<img src="pics/rubber_stopper.jpg" width=300> 

<img src="pics/screws_a.jpg" width=300> 

<img src="pics/screws_b.jpg" width=300> 

<img src="pics/pvc.jpg" width=300> 

<img src="pics/bottle.png" width=300>

<img src="pics/riffle-ito-audio.png" width=300>

<img src="pics/header-image.png" width=300>

<img src="pics/riffle-applications.png" width=300>

<img src="pics/riffle-cartoon.png" width=300>

<img src="pics/riffle-ito-label.png" width=300>

<img src="pics/riffle-ito-parts.png" width=300>




# What drove IC / placement choices
- Atmel vs ARM
- CH340 -- cheap and easy (but not easy to source)
- DS3231 -- want temp-compensated RTC to line up timestamps
- 2x7 header at end -- to allow water bottle config
- SPI and I2C breakouts at end 
- Hardware interrupts D2 and D3 for any related applications (freq-based measurements like conductivity and depth)
- EEPROM for storing configurations
- Mounting holes for gen purpose mounting

# Power management / choices
- Battery charging circuit
- But requires protective diode to allow for disconnect from USB Serial chip
- So, want to avoid voltage drop
- So, create “gen” battery input, without diode / voltage drop
- RTC alarm functionality 
- Want very low power -- mosfet on external board, mosfet on SD card, mosfet on battery measurement

# Audio out idea

https://publiclab.org/notes/donblair/09-10-2014/water-quality-coqui-voicemails

WebJack

# Other nice projects

Mayfly
Kina Smith




