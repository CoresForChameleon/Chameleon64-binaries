Scramble hardware FPGA core, ported to Turbo Chameleon 64 from MiST
by Alastair M. Robinson

This core supports multiple games, all based on the Scramble hardware.
The most iconic are Scramble, of course, and Frogger, but 19 games in 
total are supported.

MAME ROM files and associated .arc files are are required, and not
distributed with the core for copyright reasons.  The ROMs must be
converted into the correct format using each game's .mra file.  This
is processed using the mra-tools-c package which can be found at
https://github.com/mist-devel/mra-tools-c
(You don't have to build it from source - there are binaries for
both Linux and Windows in the release directory.)

Mra files for the supported games can be found in the "meta" directory.

The .arc file for each game contains the ROM filename as well as details of
any DIP switches the game supports, so when loading a game you should select
its .arc file from the file selector, instead of the .rom file.

When converting the ROM using mra-tools, you should supply the "-A" argument
to request that the .arc file be generated, like so:

> ./mra -A <game>.mra

Keys follow the MAME pattern, with keys "5" to "8" inserting coins and "1"
through "4" being player 1 through 4's start buttons, respectively.

PS/2 keyboard, C64 keyboard, joystick and CDTV pad are all supported.

Please note, Scramble hardware uses a monitor in portrait format, and this core
does the same.  This version of the core is capable of rotating and scaling
the game's playfield to fit a landscape format monitor, or you can run the 
core rotated if you have a monitor which can run in portrait format.
Screen orientation can be selected from the OSD - but please note that the new
rotation modes only work when the scandoubler is enabled.


Have fun!


Original README follows:

---------------------------------------------------------------------------------
-- 
-- Arcade: Scramble port to MiST by Gehstock
-- 10 November 2017
-- 
-- Usage:
-- Create ROM and ARC files from MAME ROM zip files using the mra utility and the MRA files.
-- Copy the RBF and the ARC files to the same folder.
-- Example: mra -A -z /path/to/mame/roms scramble.mra
-- Copy the ROM files to the root of the SD Card.
--
-- MRA utilty: https://github.com/sebdel/mra-tools-c
--
---------------------------------------------------------------------------------
-- A simulation model of Scramble hardware
-- Copyright (c) MikeJ - Feb 2007
---------------------------------------------------------------------------------
-- 
-- Only controls and OSD are rotated on Video output.
-- 
-- 
-- Keyboard inputs :
--
--   ESC         : Coin
--   F2          : Start 2 players
--   F1          : Start 1 player
--   SPACE       : Fire+Bomb

--   UP,DOWN,LEFT,RIGHT arrows : Movements
--
-- Joystick support.
-- 
---------------------------------------------------------------------------------

