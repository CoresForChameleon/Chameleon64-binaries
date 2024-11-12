Commodore VIC20 core for Turbo Chameleon 64
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
ported from the MiST core by Alastair M. Robinson


Currently supported:
~~~~~~~~~~~~~~~~~~~~
* .PRG files
* .TAP files
* .D64 files
* C64 keyboard / joystick
* Real disk drives on IEC port
* CDTV joypad
* Megacart ROM / Non-volatile RAM.

ROM
~~~
The core requires a ROM file in the root of the SD card, called
VIC20.ROM
An example ROM file can be found at 
https://github.com/mist-devel/mist-binaries/tree/master/cores/vic20
or you can create your own by joining together ROMS found in, for example,
the VICE package.  The ROMs should be concatenated in the order:
* C1541 (16k(
* Kernal PAL (8k)
* Kernal NTSC (8k)
* Basic (8k)
* Char (4k)

The ROM can also be stored in a directory called CHAM20


Megacart
~~~~~~~~
A Megacart ROM image is now supported, along with a supporting NVRAM file.
The Megacart ROM is 2 megabytes in size and should be named "MEGACART.ROM",
while the NVRAM file is 8k, and should be named "MEGACART.NV".
If these are either in the root of the SD card, or in a directory named
"CHAM20" they will be loaded at boot and the Megacart automatically activated.
If they're stored elsewhere on the SD card then they can still be loaded and 
activated manually through the menus.

The contents of the non-volatile memory will not be saved automatically - to
save it you must select the "Write NVRAM" menu option from the Megacart menu.

Please note: while the Megacart is active, the memory configuration options
in the menu will have no effect.


Disk Images
~~~~~~~~~~~
Disk images can be mounted from the menu.  If you want to dismount an image
simply enter the file selector and exit again without selecting a file.
If no disk image is mounted, then disk accesses are sent to the IEC port
instead, allowing the use of a real 1451 disk drive.


Controls
~~~~~~~~
The VIC20 keyboard is emulated via the PS/2 keyboard, and the C64 keyboard
is mapped directly.

Other keys
~~~~~~~~~~
| Function        | PS/2 keyboard | C64 keyboard | CDTV controller |
| :-------------- | :------------ | :----------- | :-------------- |
| Menu            | F12           |              | Power           |
| Restore         | F11           | Restore      |                 |
| Reset           | F10           |              |                 |
| Reset/Unload    | Shift+F10     |              |                 |
| Tape play/pause | F9            |              | Play / Pause    |

The tape play/pause function can also be accessed via the menu.
Hold the menu button for 1 second or longer to toggle the scandoubler
on or off.


There is now a keyboard-based joystick emulation - press the numlock key
to toggle this.  While the joystick emulation is enabled, the rest of the PS/2
keyboard is disabled.


Source code for this core can be found at
https://github.com/robinsonb5/VIC20_MiST/

The core is based on the FPGAArcade Replay VIC20 core by Mike Johnson and
others.  MiST port by Gyorgy Szombathelyi with contributions by Nino-porcino.

The Turbo Chameleon 64 port wraps the MiST core in a compatibility layer
(DeMiSTify, by Alastair M. Robinson), and makes very few material changes
to the core itself.
