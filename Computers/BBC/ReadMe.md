BBC Micro / Master core for Turbo Chameleon 64
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
DeMiSTified by Neurorulez (Neptuno), Rampa069 (UnAmiga Reloaded)
and Somhi (DECA).  Turbo Chameleon 64 port and enhancements by
Alastair M. Robinson


Currently supported:
~~~~~~~~~~~~~~~~~~~~
* Floppy disk images (Master mode only, SSD or DSD format.)
* MMBEEB SD card images.  .MMB files should be renamed to have the
extension .VHD - such an image named BBC.VHD in the root of the SD card
will be automatically mounted at boot.   
* C64 keyboard
* CDTV joypad
* Real-time Clock
* CMOS RAM (saved as part of the config file)

Not yet supported:
* Joysticks


ROM
~~~
The core requires a ROM file in the root of the SD card, called
BBC.ROM
An example ROM file can be found at 
https://github.com/mist-devel/mist-binaries/tree/master/cores/bbc


Configuration files
~~~~~~~~~~~~~~~~~~~
Three example configuration files are provided.  These contain both menu
settings and NVRAM settings (for BBC Master).
When the core starts it will attempt to load the BBC.CFG file from the root
of the SD card.
The supplied BBC.CFG file contains basic settings for a BBC Model B.
The other two config files are for a BBC Master with MMBeeb interface, and
a BBC Master with floppy disk emulation.
Configurations can be saved over the top of an existing config file, but
it's not currently possible to create new ones.


Disk Images
~~~~~~~~~~~
Disk images can be mounted from the menu.  They can only be accessed in
Master mode, and only if the master is configured with a disk drive rather
than the MMBEEB interface.  To change from one to the other, type the
following:
* *CO. FILE 9    (this enables the disk drive after the next reset.)
* *CO. FILE 2    (this enables the MMBeeb interface after the next reset.)


Keyboard handling
~~~~~~~~~~~~~~~~~
The keyboard is mapped roughly to match the physical location of keys on a
real BBC Micro keyboard.  
* The run/stop key on a the C64 keyboard is used as a modifier, similar to the
Fn key on a laptop.  Pressing it on its own toggles caps lock.
* The break key is mapped to prt scrn on a PS/2 keyboard, and
to run/stop-del on the C64 keyboard.
* The Commodore key is mapped to Ctrl.  This was chosen for keyboard matrix
scanning reasons, to allow keyboard combinations such as Ctrl-D-Break to be
typed.


Other keys
~~~~~~~~~~
| Function        | PS/2 keyboard | C64 keyboard  | CDTV controller |
| :-------------- | :------------ | :------------ | :-------------- |
| Menu            | F12           | Run/stop - <- | Power           |

Source code for this core can be found at
https://github.com/robinsonb5/BBC_DeMiSTify/

The core is a port of original work by Mike Sterling with major changes by 
Stephen Leary and David Banks, and further improvements by Gyorgy Szombathelyi
and Till Harbaum.

The Turbo Chameleon 64 port wraps the MiST core in a compatibility layer
(DeMiSTify, by Alastair M. Robinson), and makes very few material changes
to the core itself.
Original DeMiSTification by Neurorulez (Neptuno), Rampa069 (Unamiga Reloaded)
and Somhi (DECA), and extended to the TC64 by Alastair M. Robinson

