MiSTery Atari ST core for Turbo Chameleon 64
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
ported by Alastair M. Robinson

This is an experimental core, and while I do my utmost to make sure it works
for everyone and will try to help solve any problems that arise, you run this
core entirely at your own risk.


ROM support
~~~~~~~~~~~
You will need a TOS ROM image, which must be in the root directory of your
SD card, and named "TOS.img".
TOS versions from 1.00 to 2.06 are supported - if you want to use a 
hard-drive image then the latest is recommended - otherwise choose a version
compatible with the software you want to run.


Disk support
~~~~~~~~~~~~
Two floppy drives are currently supported.
Two hard disks are also supported
Disk images can be unmounted simply by entering the file selector and leaving
it again without selecting a file.


Keyboard
~~~~~~~~
PS/2 and C64 keyboards are supported.
The run/stop key acts a bit like the "fn" key on a laptop.  Press run/stop and
the top left arrow key simultaneously to enter the menu.


Buttons
~~~~~~~
The rightmost button on the Chameleon cartridge resets the core.
The leftmost button (or the Power button on a CDTV pad) toggles the menu.
Pressing the middle and rightmost button simultaneously will return to the
Chameleon core.


Source code for this core can be found at
https://github.com/robinsonb5/MiSTery


The core was originaly written by Gyorgy Szombathelyi, based on the earlier
MiST Atari ST core by Till Harbaum, and incorporating components written by
Jorge Cwik.


The Turbo Chameleon 64 port wraps the MiST core in a compatibility layer
(DeMiSTify, by Alastair M. Robinson), with very few changes to the core
itself.

