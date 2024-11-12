---------------------------------------------------------------------------------
-- 
-- Arcade: Moon Patrol port to MiSTer by Sorgelig
-- 27 November 2017
-- Ported to Turbo Chameleon 64 by Alastair M. Robinson
-- December 2022
-- 
---------------------------------------------------------------------------------
-- Uses PACE framework by http://pacedev.net/
---------------------------------------------------------------------------------
-- Moon patrol sound board by Dar (darfpga@aol.fr)
-- http://darfpga.blogspot.fr
---------------------------------------------------------------------------------
-- cpu68 - Version 9th Jan 2004 0.8
-- 6800/01 compatible CPU core 
-- GNU public license - December 2002 : John E. Kent
---------------------------------------------------------------------------------

## ROMS:

ROMs are not included. In order to use this arcade care, you need to provide the
correct ROM file.

To create a suitable .ROM file, use the mra-tools-c utility which can be found at
https://github.com/mist-devel/mra-tools-c
Binaries for Window and Linux can be found in the releases directory.
You will need the mpatrol.zip ROM file from a MAME (v0.220) ROM set, and the
provided .mra file.  The resulting mpatrol.rom file should be placed on the SD card.


## Keyboard inputs:

Coin and Start buttons are mapped to match MAME,
so 5 & 6 keys for coin, and 1 & 2 keys for start.

Directions are mapped to the cursor keys for joystick 1, and WASD for joystick 2.

In addition, on the C64 keyboard, joystick 1 is mapped to IJKL

Fire buttons are mapped to Right Ctrl / Alt Gr, and Left Ctrl / Alt.

Additionally, on the C64 keyboard the first set of fire buttons are
mapped to . & /, as well as B & N, for right- or left-handed play
when using the IJKL keys.

The second set of fire buttons are mapped to left shift / Commodore keys, and
also C & V, for right- or left-handed play when using the WASD keys.

The Joystick and CDTV pad are also supported.
 

