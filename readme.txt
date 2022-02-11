M#"""""""'M           dP                MM'""""'YMM                         dP 
##  mmmm. `M          88                M' .mmm. `M                         88 
#'        .M .d8888b. 88  .dP  .d8888b. M  MMMMMooM .d8888b. 88d888b. .d888b88 
M#  MMMb.'YM 88'  `88 88888"   88'  `88 M  MMMMMMMM 88'  `88 88'  `88 88'  `88 
M#  MMMM'  M 88.  .88 88  `8b. 88.  .88 M. `MMM' .M 88.  .88 88       88.  .88 
M#       .;M `88888P8 dP   `YP `88888P8 MM.     .dM `88888P8 dP       `88888P8 
M#########M                             MMMMMMMMMMM                            


BakaCard ("SD2PS2") is a very simple SD card to Playstation2 memory card adapter based
on the MX4SIO documentation and various parts of SD card documentation I could get my
hands on, with the goal of being easy and cheap to manufacture. 

--- "EASY" and "CHEAP" ---

Every part in this board can be sourced via LCSC. While you don't have to use LCSC,
it's a very convenient measure of "how well can I get this part."

The SD card holder chosen is a Hirose part DM3AT-SF-PEJM5. This is the *normal* version
of the one used by Trisaster. This part is 1:1 compatible with a second-source part,
the Xunpu TF-111. Their major difference is the orientation of the part off the reel for
pick and place.

LEDs are side-mounted 0603 (1608 metric) ones from Lite-On. While these don't have a
second source, a properly oriented top-fire LED will do the job. Alternatively, the
Kingbright APGA1602SEC/E/KA (digikey PN 754-1816-1-ND) will do for the red. The Green
version is APGA1602CGC/KA (754-1820-1-ND). 

All others are jellybean parts that can be sourced wherever. 

The NPN transistor has SMT pads for two different sizes, SO-23 and SO-723. It can
comfortably fit SO-523 parts as well. 

--- MANUFACTURING ---

Pick your pick & place shop. To fit this into a legit Playstation2 shell, have this made
from 1.1mm thick FR4 with either ENIG Gold or lead-free HASL. The ENIG Gold looks pretty
but comes at a higher cost. 

--- ERRORS IN REV A ---

If you have a Rev A board, you will find that there is a glaring bug: I've connected VSS
(ground) to DO and DAT0 to nothing!

To fix:

* Cut the trace to pin 6 on the SD card slot just below C1.
* Run a wire from pin 6 on the SD card slot to GND (use the pad on C1)
* Run a wire from pin 7 to the via just below C1. 

--- LICENSE & COPYRIGHT ---

Credit where credit is due: Takeshi did the OG hardware. I took the documentation from
Trisaster.de and redid the circuit. I'm not the only one, and others have replicated
much of the work. 

As for this design: I want as many people to have the *clean* source to this hardware.
Not just gerbers, the whole kit and kaboodle. As such, here's the ugly bit: Copyrights.

I've chosen the CERN OHL V2 Strongly Reciprocal. What's this mean? 

* You're free to make the thing, so long as you retain any notices of where to get
  the source for the thing. The silkscreen contains the GitHub URL for this project.
* If you modified it, fork my github repo and push your changes up. If I've vanished,
  do your best to put your copy of the sources up.
* If you do change things, make sure to note what you've changed. 
* Your changes will remain under the CERN OHL V2, where legally allowed.

My goal with this is not to restrict people from creating new versions of the card. The
opposite is true: I want to make sure that people can continue to refine and fix issues
with the card design.


~~ The legal bits ~~

Copyright Morgan "indrora" Gangwere and contributors, 2022

This source describes Open Hardware and is licensed under the CERN-OHL-S v2.

You may redistribute and modify this source and make products using it under
the terms of the CERN-OHL-S v2 (https://ohwr.org/cern_ohl_s_v2.txt).

This source is distributed WITHOUT ANY EXPRESS OR IMPLIED WARRANTY,
INCLUDING OF MERCHANTABILITY, SATISFACTORY QUALITY AND FITNESS FOR A
PARTICULAR PURPOSE. Please see the CERN-OHL-S v2 for applicable conditions.

Source location: https://github.com/indrora/bakacard

As per CERN-OHL-S v2 section 4, should You produce hardware based on this
source, You must where practicable maintain the Source Location visible
on the PCB. Appreciated is a link to the Source Location in user-facing
documentation, store pages, etc. 