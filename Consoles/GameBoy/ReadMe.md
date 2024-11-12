Gameboy core for Turbo Chameleon 64
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
ported from the MiST core by Alastair M. Robinson

This is an experimental core, and while I do my utmost to make sure it works
for everyone and will try to help solve any problems that arise, you run this
core entirely at your own risk.


ROM support
~~~~~~~~~~~
To run Gameboy Colour games you will need a suitable BIOS file in the root
directory of your SD card, named "gbc_bios.bin"

Optionally, you can also arrange for a ROM to run automatically - just copy
it to the root of the SD card, and rename it to autoboot.gb.  (The supplied
autoboot.gb file shows a scrolltext with thanks to supporters, and core
credits.)


Controls
~~~~~~~~
Since the Turbo Chameleon 64 can't support more than three gamepad buttons
via the DB9 ports, the extra buttons are mapped as follows:

Gamepad 1
~~~~~~~~~
| Gamepad button | PS/2 keyboard | C64 keyboard | CDTV controller |
| :------------- | :------------ | :----------- | :-------------- |
| Start          | Enter         |              | Play            |
| Select         | Right shift   |              | Volume up       |
| Button A       | Right Ctrl    |              | Button B        |
| Button B       | Right Alt     |              | Button A        |

Gamepad 2
~~~~~~~~~
| Gamepad button | PS/2 keyboard | C64 keyboard | CDTV controller |
| :------------- | :------------ | :----------- | :-------------- |
| Start          | Caps Lock     |              | Play           |
| Select         | Left shift    |              | Volume up      |
| Button A       | Left Alt      |              | Button B        |
| Button B       | Left Ctrl     |              | Button A        |


Other keys
~~~~~~~~~~
| Function       | PS/2 keyboard | C64 keyboard | CDTV controller |
| :------------- | :------------ | :----------- | :-------------- |
| Menu           | F12           |              | Power           |

Hold the menu button for 1 second or longer to toggle the scandoubler
on or off.

To return to the Chameleon core, press the middle and right hand buttons
on the Chameleon cartridge simultaneously.


Source code for this core can be found at
https://github.com/robinsonb5/gameboy


The core was originaly written by Till Harbaum with further development
and fixes by Gyorgy Szombathelyi, Bruno Duarte Gouveia and paulb-nl.
The audio implementation is from the PACE project, and the T80 CPU
core is by Daniel Wallner and Mike Johnson.

The Turbo Chameleon 64 port wraps the MiST core in a compatibility layer
(DeMiSTify, by Alastair M. Robinson), with very few changes to the core
itself.  The only major change is that the GBC BIOS is now loaded from
SD card instead of being embedded, since the core otherwise requires
more RAM blocks than are available on the TC64.

