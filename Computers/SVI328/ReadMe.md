# Spectravideo SV328 

Ported from a MiSTer core originally by Alan Steremberg, using components
written by Daniel Wallner, Arnim Lauger, Jotego, Sorgelig and others.

Ported to SiDi and DeMiSTify by Ramon Martinez / RW-FPGA-Team

Ported to Turbo Chameleon 64, migrating Cassette storage to SDRAM and addition
of Cassette audio by Alastair M. Robinson


## Getting started

You will need an original SVI 328 ROM image on your SD card, called SVI328.ROM
A suitable ROM can be found at 
http://www.armory.com/~rstevew/Public/Roms/spectravideo/
(Any of the three svi1xx.bin ROMs will do, but must be renamed, as above.)
These files can also be found (on rather sketchy download sites, so beware) by
searching for "svi328.zip"

You will also need some suitable Spectravideo software, either in Cassette
image form (filename must end in .CAS), or in cartridge form (filename may end
in .ROM or .BIN).

A comprehensive Spectravideo software collection can be found at Archive.org

Once you've loaded a Cassette image file from the OSD, type "cload" at the
BASIC prompt to start loading from cassette.


## Controls

Both PS/2 and C64 keyboards are supported, as well as C64 joysticks and a
CDTV control pad.

The joystick can also be emulated using the PS/2 keyboard - this can be
toggled using the Num Lock key on the numeric keypad.


Source code can be found at:
https://github.com/robinsonb5/SVI328-Demistify

