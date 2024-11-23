Sega Master System core for Turbo Chameleon 64
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
ported from the MiST/MiSTer SMS core by Alastair M. Robinson

Controls
~~~~~~~~
Since the Turbo Chameleon 64 can't support more than three gamepad buttons
via the DB9 ports, the extra buttons are mapped as follows:

Gamepad 1
~~~~~~~~~
| Gamepad button | PS/2 keyboard | C64 keyboard | CDTV controller |
| :------------- | :------------ | :----------- | :-------------- |
| Start          | Enter         | Return       | Play*           |
| Select         | Right shift   | Right shift  | Volume up*      |
| Button A       | Right Ctrl    |              | Button A        |
| Button B       | Right Alt     |              | Button B        |

Gamepad 2
~~~~~~~~~
| Gamepad button | PS/2 keyboard | C64 keyboard | CDTV controller |
| :------------- | :------------ | :----------- | :-------------- |
| Start          | Caps Lock     | Run/Stop     | Play*           |
| Select         | Left shift    | Left shift   | Volume up*      |
| Button A       | Left Alt      |              | Button A        |
| Button B       | Left Ctrl     |              | Button B        |

Other keys
~~~~~~~~~~
| Function       | PS/2 keyboard | C64 keyboard | CDTV controller |
| :------------- | :------------ | :----------- | :-------------- |
| Menu           | F12           | <-(top left) | Power           |

Hold the menu button for 1 second or longer to toggle the scandoubler
on or off.

Source code for this core can be found at
https://github.com/robinsonb5/SMS_MiSTer/

The MiST port contains code and contributions from:
Till Harbaum, Alexey Melnikov, theflynn49, Gyorgy Szombathelyi,
GreyRogue, Shane Lynch, Enforcer831, kitrinx,
SegaSnatcher, Yimmers, blue212, SegaSnatcher and Alastair Robinson

The Turbo Chameleon 64 port wraps the MiST core in a compatibility layer
(DeMiSTify, by Alastair M. Robinson), and makes no material changes to the
core itself.

