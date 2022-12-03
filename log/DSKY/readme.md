# DSKY details

### Planning
24 NOV 2022
I am current trying to decide on the display technology.  While I would love to use an electroluminescent display, I am concerned about the long-term durability of the display on account of vibration, Arizona heat, and extended UV exposure from the sun.  There appears to be a decent level of interest around the DSKY, enough so that several individuals have created projects to replicate the unit.  Most of these are one-off devices, and the larger projects offering units for sale tend to price the devices high enough to discourage most would-be users.  Additionally, I require a unit which will control external devices via GPIO, as well as read from various sensor inputs, thus there is a need to roll my own.

### Goals
- [ ] simple to replicate
- [ ] low cost
- [ ] display quality
    - [ ] high contrast
    - [ ] bright
    - [ ] crisp, well-defined segments
    - [ ] true-to-original color and character dimensions
- [ ] durable

### Current concept
I am investigating the potential to use surface-mount LEDs covered by a 3D-printed shadow mask.  Once the mask is placed over the PCB, the light paths in the mask can be filled with a translucent substance to act as a diffuser.  If the desired image sharpness cannot be obtained this way, then the glass can have copper foil affixed via epoxy and then the copper can be etched to create a very sharp mask that can rest just above the 3D-printed mask.  There will be 163 segments to control, most of which can be driven with 7-segment drivers and code, however I have a desire to avoid tricks like charlieplexing due to the desire to maximize brightness.

As an initial implementation, I am going to use a 256x128 pixel graphical VFD.  


### Task Timeline
#### 2022.W47
- [ ] get VFD working with dev board
- [ ] determine refresh rate for fullscreen update
- [ ] build keyboard
