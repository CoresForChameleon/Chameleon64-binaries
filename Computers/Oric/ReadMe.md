# Oric 48K in MiST and SiDi FPGA

Oric-1 and Oric Atmos re-implementation on a modern FPGA.

Ported to Turbo Chameleon 64 by Alastair M. Robinson

## What's supported

Oric 1, Oric Atmos and Microdisc are fully functional.
* **ULA HCS10017**.
* **VIA 6522**.
* **CPU 6502**.
* Full 64KB of **RAM**.
* Keyboard managed by GI-8912.
* Sound (**AY-3-8910**).
* switchable **ROM** (between 1.1a ATMOS version and 1.0 ORIC 1 version).
* Tape image loading
* Oric Microdisc implementation vía **CUMULUS**
* Disc Read / Write operations fully supported with EDSK (The same as amstrad cpc) format.
* Disc Sedoric/OricDOS Operating System Loading fully working


## Getting started

You will need an Oric ROM image on the SD card, called Oric.rom - a suitable
ROM file can be found alongside the MiST core at:
https://github.com/mist-devel/mist-binaries/tree/master/cores/oric


## Keyboard shortcuts

   * F10 (Run/Stop + F3 on C64 keyboard) - NMI button, acts like original ORIC NMI
   * F11 (Run/Stop + F7 on C64 keyboard) - Reset. Use F11 to reboot once a DSK is selected at OSD
   * F12 (Run/Stop + <- on C64 keyboard) - OSD Main Menu.


## Using disk images

Disk images must be in the defacto standard "edsk" format (also known as "Amstrad CPC Extended Format")
Regular disk images can be converted to CPC edsk format using the HxCFloppyEmulator software which can be
found at https://hxc2001.com/download/floppy_drive_emulator/HxCFloppyEmulator_soft.zip

To use a disk image:
   * Activate the FDC controller in the OSD menu
   * Select the disk image using the "Mount drive A:" item in the OSD menu
   * Reset the Oric using F11 or the "Reset" menu item.


## Credits
   The Oric Fpga preservation TEAM
   * Ron Rodritty:  Team coordination and QA testing.
   * Fernando Mosquera: FPGA guru.
   * Subcritical: Verilog and VHDL.
   * ManuFerHi: Hardware consulting.
   * Chema Enguita: Oric Software gurú
   * SiliceBit: Oric hardware Gurú
   * ZXMarce: Hardware support 24/7...
   * Ramón Martínez:  Oric hardware, Some software, and fpga coding.
   * Slingshot: SDRAM work and advisor.

* Kudos to: Sorgelig, Gehstock, DesUBIKado, RetroWiki and friends.


## Software

Some example disk images can be found at: https://github.com/rampa069/Oric_Mist_48K/tree/master/dsk
* **SEDORIC 4.0** operating System disk image redistributed with permission from Symoon.
* **Blake's 7** game, redistributed with permission of chema enguita you can download manual and additional info from [Defence force](http://www.defence-force.org/index.php?page=games&game=blakes7)
* **Oricium** game, redistributed with permission of chema enguita you can download manual and additional info from [Defence force](http://www.defence-force.org/index.php?page=games&game=oricium)
* **Space:1999** game, redistributed with permission of chema enguita you can download manual and additional info from [Defence force](http://www.defence-force.org/index.php?page=games&game=space1999)
* **1337** game, redistributed with permission of chema enguita you can download manual and additional info from [Defence force](http://www.defence-force.org/index.php?page=games&game=1337)
* **Torreoscura** game, redistributed with permission of Bieno. you can download manual and additional info from [itch.io](https://commodore-plus.itch.io/torreoscura-eng-c64-oric)
* **El prisionero** game, redistributed with permission of Bieno. you can download manual and additional info from [itch.io](https://commodore-plus.itch.io/el-prisionero)

