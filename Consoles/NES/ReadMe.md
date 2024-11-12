NES for Turbo Chameleon 64
~~~~~~~~~~~~~~~~~~~~~~~~~~
ported from the MiST NES core by Alastair M. Robinson

Controls
~~~~~~~~
Since the Turbo Chameleon 64 can't support more than three gamepad buttons
via the DB9 ports, the extra buttons are mapped as follows:

Gamepad 1
~~~~~~~~~
| Gamepad button | PS/2 keyboard | C64 keyboard | CDTV controller |
| :------------- | :------------ | :----------- | :-------------- |
| Start          | Enter         | Return       | Play*           |
| Select         | Right shift   | =            | Volume up*      |
| Button A       | Right Alt     | B   /        | Button B        |
| Button B       | Right Ctrl    | N   .        | Button A        |
| Up             | Up            | I            | Up              |
| Down           | Down          | J            | Down            |
| Left           | Left          | K            | Left            |
| Right          | Right         | L            | Right           |

Gamepad 2
~~~~~~~~~
| Gamepad button | PS/2 keyboard | C64 keyboard | CDTV controller |
| :------------- | :------------ | :----------- | :-------------- |
| Start          | Caps Lock     | Ctrl         | Play*           |
| Select         | Left shift    | Run/Stop     | Volume up*      |
| Button A       | Left Ctrl     | C   L Shift  | Button B        |
| Button B       | Left Alt      | V  Commodore | Button A        |
| Up             | Up            | W            | Up              |
| Down           | Down          | A            | Down            |
| Left           | Left          | S            | Left            |
| Right          | Right         | D            | Right           |

Other keys
~~~~~~~~~~
| Function       | PS/2 keyboard | C64 keyboard | CDTV controller |
| :------------- | :------------ | :----------- | :-------------- |
| Menu           | F12           | <-(top left) | Power           |

Hold the menu button for 1 second or longer to toggle the scandoubler
on or off.

The scandoubler can also be made to default to off by placing a file named
"15khz.cfg" in the root of the SD card.  (The file's contents aren't
important - just its presence or otherwise.)


Source code for this core can be found at https://github.com/robinsonb5/nes/

The original core by Luddes is described on his FPGANES blog at
http://fpganes.blogspot.de for details. The original source code can be found
at https://github.com/strigeus/fpganes.
Many changes ported from https://github.com/MiSTer-devel/NES_MiSTer.
The MiST version can be found at https://github.com/mist-devel/nes

The Turbo Chameleon 64 port wraps the MiST core in a compatibility layer
(DeMiSTify, by Alastair M. Robinson), and makes no material changes to the
core itself.

