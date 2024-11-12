Irem M62 hardware FPGA core
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Ported to Turbo Chameleon 64 from MiST by Alastair M. Robinson

Based on old PACE code by Mark McDougall(tcdev),
enhanced by Gyorgy Szombathelyi in March 2020.

Games supported:
- Lode Runner 1-4
- Kung Fu Master
- Horizon
- Battle Road
- Spelunker 1-2
- Kid Niki
- Youjyudn

This core is an extremely tight fit on the Turbo Chameleon 64.  It *just* fits
on V1 hardware, but unfortunately I've been unable to make it fit on V2
hardware without compromises.  For V2 hardware I've reduced the number of
sprites in the sprite hardware.  To the best of my knowledge this only affects
the game "Horizon" which requires 64 sprites - so if you try and play this game
on V2 hardware you'll find yourself being killed by enemies you can't see.
The other games should all be fully playable, however.


ROMS
~~~~

MAME ROM files and associated .arc files are required, and not
distributed with the core for copyright reasons.

The ROMs should be from a MAME 0.216 set (newer versions may or may not work)
and must be converted into the correct format using each game's .mra file.
This is processed using the mra-tools-c package which can be found at
https://github.com/mist-devel/mra-tools-c
(You don't have to build it from source - there are binaries for
both Linux and Windows in the release directory.)

Mra files for the supported games can be found in the "meta" directory.

The .arc file for each game contains the ROM filename as well as details of
any DIP switches the game supports, so when loading a game you should select
its .arc file from the file selector, instead of the .rom file.

When converting the ROM using mra-tools, you should supply the "-A" argument
to request that the .arc file be generated, like so:

> ./mra -A <game>.mra

Having converted the ROMs, copy them to the SD card.  At startup the core
will attempt to load "IremM62.arc" and if that fails, fall back to
"LOAD RUNNER.ARC" (actually "LOADRU~1.ARC" since it uses the FAT filesystem
short filename).  This means you can choose which game to load at power-up
by copying its .arc file to IremM62.arc.
Please note, the core won't output a video signal until a game ROM has been
loaded, so you will need to make sure one of those two files is available,
along with its associated .rom file.


Keys
~~~~

Keys follow the MAME pattern, with keys "5" to "8" inserting coins and "1"
through "4" being player 1 through 4's start buttons, respectively.

PS/2 keyboard, C64 keyboard, joystick and CDTV pad are all supported.

Please note, some games supported by this core used a monitor in
portrait format, and this core does the same.  Rotating the game field isn't
possible on the Turbo Chameleon 64 hardware.


Source code
~~~~~~~~~~~
The source for this port, and others from Gehstock's multi-core Mist_FPGA
repository can be found at:
https://github.com/robinsonb5/Mist_FPGA/tree/2024_01_IremM62

Have fun!

