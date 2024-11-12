Amstrad core for Turbo Chameleon 64
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Ported by Alastair M. Robinson from the MiST Amstrad_alt core, which was
written by Alexey Melnikov, building upon previous work by Renaud Hélias,
and with subsequent improvements and maintenance by Gyorgy Szombathelyi.


Currently supported:
~~~~~~~~~~~~~~~~~~~~
* Floppy disk images
* Cassette images (partial support)
* C64 keyboard
* CDTV joypad
* Joysticks


ROM
~~~
The core requires a ROM file in the root of the SD card, called
AMSTRAD.ROM
An example ROM file can be found at 
https://github.com/mist-devel/mist-binaries/tree/master/cores/amstrad_alt


Disk Images
~~~~~~~~~~~
Disk images can be mounted from the menu.  To list the contents of a disk,
type `cat`.
To load and run a program from disk, type `run "programname` (note the lack
of a closing quote)


Keyboard handling
~~~~~~~~~~~~~~~~~
The keyboard is mapped roughly to match the physical location of keys on a
real Amstrad keyboard.  
* The run/stop key on a the C64 keyboard is used as a modifier, similar to the
Fn key on a laptop.  Pressing it on its own toggles caps lock.


Other keys
~~~~~~~~~~
| Function        | PS/2 keyboard | C64 keyboard  | CDTV controller |
| :-------------- | :------------ | :------------ | :-------------- |
| Menu            | F12           | Run/stop - <- | Power           |

Source code for this core can be found at
https://github.com/robinsonb5/Amstrad_MiST

The Turbo Chameleon 64 port wraps the MiST core in a compatibility layer
(DeMiSTify, by Alastair M. Robinson), and makes very few material changes
to the core itself.

