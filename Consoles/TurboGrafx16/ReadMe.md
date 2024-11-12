PC Engine / TurboGrafx16 / SuperGrafx / SuperCD core for Turbo Chameleon 64
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
ported from the MiST core by Alastair M. Robinson

This is an experimental core, and while I do my utmost to make sure it works
for everyone and will try to help solve any problems that arise, you run this
core entirely at your own risk.

ROM support
~~~~~~~~~~~
PC Engine, TurboGrafx and SuperGrafx ROMs are supported.  The core
automatically adapts to the appropriate ROM type, but in the case
of SuperGrafx ROMs it uses the filename to do so - the ROM's file
extension *must*, therefore, be .sgx


CDROM support
~~~~~~~~~~~~~
This core has basic support for CROM images in bin/cue format.
Currently the image must have exactly one .cue file and exactly
one .bin file - multiple .bin files and .wav files are not currently
supported.
To use CDROM images you will have to load a SuperCDROM BIOS image - such
as syscard3.pce - as though it were a game ROM.  Once the BIOS is running
select a .cue file using the "Mount CD Image" menu option, and then press
the "Run" button ("Enter" on a PS/2 keyboard, the Play button on a CDTV pad)

The memory map of the machine adapts automatically to the type of ROM 
selected; this means SuperGrafx ROMs won't run correctly while a CD image is
mounted.  You can unmount a CD image simply by selecting the "Mount CD Image"
menu option, and exiting the file selector without selecting a file.

Controls
~~~~~~~~
Since the Turbo Chameleon 64 can't support more than three gamepad buttons
via the DB9 ports, the extra buttons are mapped as follows:

Gamepad 1
~~~~~~~~~
| Gamepad button | PS/2 keyboard | C64 keyboard | CDTV controller |
| :------------- | :------------ | :----------- | :-------------- |
| Run            | Enter         |              | Play            |
| Select         | Right shift   |              | Volume up       |
| Button I       | Right Alt     |              | Button B        |
| Button II      | Right Ctrl    |              | Button A        |

Gamepad 2
~~~~~~~~~
| Gamepad button | PS/2 keyboard | C64 keyboard | CDTV controller |
| :------------- | :------------ | :----------- | :-------------- |
| Run            | Caps Lock     |              | Play           |
| Selecr         | Left shift    |              | Volume up      |
| Button I       | Left Ctrl     |              | Button B        |
| Button II      | Left Alt      |              | Button A        |

Since the Chameleon lacks a way to connect gamepads with more than three
buttons and only buttons A and B on the CDTV pad can be used in combination
with the D pad, I haven't made any attempt to support emulation of six button
pads.

Other keys
~~~~~~~~~~
| Function       | PS/2 keyboard | C64 keyboard | CDTV controller |
| :------------- | :------------ | :----------- | :-------------- |
| Menu           | F12           |              | Power           |

Hold the menu button for 1 second or longer to toggle the scandoubler
on or off.


Source code for this core can be found at
https://github.com/robinsonb5/TurboGrafx16_NoSoC/


The core was originaly written by Gregory Estrade, with further development
by Alexey Melnikov, greyrogue, György Szombathelyi, Sergey Dvodnenko,
David Shadoff, Jamie Dickson, M-Walrus, paulb-nl, and akramer

The Turbo Chameleon 64 port wraps the MiST core in a compatibility layer
(DeMiSTify, by Alastair M. Robinson), with a few changes to the core itself,
which include improved audio quality, reduction in the number of RAM blocks
used, and changes to the video pipeline.

