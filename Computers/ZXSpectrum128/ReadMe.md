ZX Spectrum 128k core for Turbo Chameleon 64
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Ported by Alastair M. Robinson from the MiST ZX Spectrum 128K core, which was
written by Alexey Melnikov, building upon previous work by Till Harbaum and
others, and subsequent improvements and maintenance by Gyorgy Szombathelyi.


Currently supported:
~~~~~~~~~~~~~~~~~~~~
* Floppy disk images
* Cassette images
* Snapshots
* C64 keyboard
* CDTV joypad
* Joysticks


ROM
~~~
The core requires a ROM file in the root of the SD card, called
SPECTRUM.ROM
An example ROM file can be found at 
https://github.com/mist-devel/mist-binaries/tree/master/cores/spectrum


Keyboard handling
~~~~~~~~~~~~~~~~~
The keyboard is mapped roughly to match the physical location of keys on a
real Spectrum keyboard.

* The run/stop key on a the C64 keyboard is used as a modifier, similar to the
Fn key on a laptop.  Pressing it on its own toggles caps lock.


Other keys
~~~~~~~~~~
| Function        | PS/2 keyboard | C64 keyboard     | CDTV controller |
| :-------------- | :------------ | :--------------- | :-------------- |
| Menu            | F12           | Run/stop - <-    | Power           |
| (Un)Pause Tape  | F1            | F1, Run/stop - 1 |                 |
| Tape rewind     | F2            | F2, Run/stop - 2 |                 |
| Tape forward    | F3            | F3, Run/stop - 3 |                 |
| Turbo off       | F4            | F4, Run/stop - 4 |                 |
| Turbo x2        | F5            | F5, Run/stop - 5 |                 |
| Turbo x4        | F6            | F6, Run/stop - 6 |                 |
| Turbo x8        | F7            | F7, Run/stop - 7 |                 |
| Turbo x16       | F8            | F8, Run/stop - 8 |                 |
| (Un)Pause       | F9            | Run/stop - 9     |                 |
| Snapshot menu   | F10           | Run/stop - 0     |                 |
| Multiface 128   | RShift-F10    |                  |                 |
| Warm reset      | F11           |                  |                 |
| Cold reset      | Alt-F11       |                  |                 |
| Reset/autoload  | Ctrl-F11      |                  |                 |


Not yet supported
~~~~~~~~~~~~~~~~~
VHD disk images or direct SD card access for use with esxDOS


Source code for the core can be found at:
https://github.com/robinsonb5/ZX_Spectrum-128K_MIST

The Turbo Chameleon 64 port wraps the MiST core in a compatibility layer
(DeMiSTify, by Alastair M. Robinson), and makes very few material changes
to the core itself.

