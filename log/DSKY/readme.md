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

MCU selected is STM32H743ZI.

VFD is driven via an 8bit parallel peripheral, using hardware acceleration.  Soon to attempt DMA.  Differential framebuffer currently averages 180FPS for most content.

<a href="https://www.youtube.com/watch?feature=player_embedded&v=XFZPoMXJEX4" target="_blank">
 <img src="https://img.youtube.com/vi/XFZPoMXJEX4/0.jpg" alt="Watch the video" width="240" height="180" border="10" />
</a>


### Log
#### 2022.347
I decided early on that I was going to use a graphical VFD for my display, and augment the original DSKY's segmented numeric display with text for my Amateur radio telemetry as well as on-screen configuration menus and other tasks in an effort to make the system more usable while still providing for the old-school aesthetic.

One thing that I wanted was a proper 3D engine, but I have had a miserable time trying to make use of existing libraries and have elected instead to read up on the science of 3D rasterization and roll my own completely from scratch.  Should anyone look upon this project in the future, on account of whatever 3D performance I manage to squeeze out of this microcontroller, I cannot stress how much more of a service one will do to themselves to follow a similar process and write their own engine from the ground up instead of trying to shove a square peg into a round hole by copy-pasta of someone else's code.

### Task Timeline
#### 2022.W47
- [x] get VFD working with dev board
- [x] determine refresh rate for fullscreen update
- [ ] build keyboard
#### 2022.W50
- [x] improve framebuffer code (currently 60fps for full screen refresh)
- [x] code screensavers (need eyecandy, plus i don't want to burn in the display)
- [ ] add initial program modes
- [ ] code astronomical formulae into system and test
- [ ] integrate GPS
- [ ] integrate IMU
- [ ] add Floyd-Steinberg dithering
- [ ] add 3D rasterization
