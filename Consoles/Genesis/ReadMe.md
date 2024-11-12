Sega Megadrive / Genesis core for Turbo Chameleon 64
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
ported from the MiST core by Alastair M. Robinson

Controls
~~~~~~~~
Since the Turbo Chameleon 64 can't support more than three gamepad buttons
via the DB9 ports, the extra buttons are mapped as follows:

Gamepad 1
~~~~~~~~~
| Gamepad button | PS/2 keyboard | C64 keyboard | CDTV controller |
| :------------- | :------------ | :----------- | :-------------- |
| Start          | Enter         | Return       | Play*           |
| Button A       | Right shift   | Right shift  | Volume up*      |
| Button B       | Right Ctrl    |              | Button A        |
| Button C       | Right Alt     |              | Button B        |

Gamepad 2
~~~~~~~~~
| Gamepad button | PS/2 keyboard | C64 keyboard | CDTV controller |
| :------------- | :------------ | :----------- | :-------------- |
| Start          | Caps Lock     | Run/Stop     | Play*           |
| Button A       | Left shift    | Left shift   | Volume up*      |
| Button B       | Left Alt      |              | Button A        |
| Button C       | Left Ctrl     |              | Button B        |

Since the Chameleon lacks a way to connect gamepads with more than three
buttons and only buttons A and B on the CDTV pad can be used in combination
with the D pad, I haven't made any attempt to support emulation of six button
pads.

Other keys
~~~~~~~~~~
| Function       | PS/2 keyboard | C64 keyboard | CDTV controller |
| :------------- | :------------ | :----------- | :-------------- |
| Menu           | F12           | <-(top left) | Power           |

Hold the menu button for 1 second or longer to toggle the scandoubler
on or off.

Source code for this core can be found at
https://github.com/robinsonb5/fpgagen/

The core was original written by Gregory Estrade, with the sound chip
implementation by Jotego.  The MiST port contains code and contributions
from Till Harbaum, Gyorgy Szombathelyi and Phoboz.

The Turbo Chameleon 64 port wraps the MiST core in a compatibility layer
(DeMiSTify, by Alastair M. Robinson), and makes no material changes to the
core itself.

