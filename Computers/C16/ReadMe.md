Commodore C16 / Plus 4 core for Turbo Chameleon 64
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
ported from the MiST core by Alastair M. Robinson


Currently supported:
~~~~~~~~~~~~~~~~~~~~
.PRG files
.TAP files
.D64 files
6581 and 8580 SID emulation (from the MiSTer C64 core)
C64 keyboard / joystick
C16 keyboard on the Docking Station (separate adapter needed)
Real disk drives on IEC port
CDTV joypad


ROM
~~~
The core requires a ROM file in the root of the SD card, called
C16.ROM
An example ROM file can be found at 
https://github.com/mist-devel/mist-binaries/tree/master/cores/c16
or you can create your own by joining together ROMS found in, for example,
the VICE package.  The ROMs should be concatenated in the order:
* C1541
* Kernal
* Basic
* Function LOW
* Function HIGH
The function ROMs are optional - they provide the inbuilt software found in 
the Commodore Plus-4.  Without the core will be a C16 (albeit one equipped,
optionally, with 64k of RAM.)


Disk Images
~~~~~~~~~~~
Disk images can be mounted from the menu.  If you want to dismount an image
simply enter the file selector and exit again without selecting a file.
If no disk image is mounted, then disk accesses are sent to the IEC port
instead, allowing the use of a real 1451 disk drive.


Controls
~~~~~~~~
The C16 keyboard is emulated via the PS/2 keyboard, and the C64 keyboard
is more-or-less mapped directly.  This means that the keys on the C64
will do what the equivalent key on a C16 keyboard in that location would do.
In other words, the keys' function won't match what's printed on the C64
keycaps!
(If you have a real C16 keyboard connected to the Docking Station with a
suitable adapter, the menu allows you to disable this remapping by changing
the keyboard type from "C64" to "C16")


Other keys
~~~~~~~~~~
| Function        | PS/2 keyboard | C64 keyboard | CDTV controller |
| :-------------- | :------------ | :----------- | :-------------- |
| Menu            | F12           |              | Power           |
| Play/Pause tape |               |              | Play/Pause      |

The tape play/pause function can also be accessed via the menu.
Hold the menu button for 1 second or longer to toggle the scandoubler
on or off.


Source code for this core can be found at
https://github.com/robinsonb5/c16/

The core is based around a TED implementation by Istvan Hegedus, and includes
components writted by Mark McDougall, Michel Stempin, Stephen A. Edwards,
Gideon Zweijtzer, Daniel Wallner, MikeJ, ehenciak, DarFPGA, Alexey Melnikov,
Till Harbaum, Gyorgy Szombathelyi and Nino-porcino.

The Turbo Chameleon 64 port wraps the MiST core in a compatibility layer
(DeMiSTify, by Alastair M. Robinson), and makes very few material changes
to the core itself.  It does, however, include the newer SID implementation
from the MiSTer C64 core, by Alexey Melnikov, with the lookup tables'
representation adjusted to be more space efficient by Alastair M. Robinson.

