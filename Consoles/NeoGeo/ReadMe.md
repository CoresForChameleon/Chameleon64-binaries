# [SNK Neo Geo](https://en.wikipedia.org/wiki/Neo_Geo_(system)) for [MiST FPGA](https://github.com/mist-devel/mist-board/wiki)

This is the port of the [NeoGeo FPGA implementation](https://github.com/MiSTer-devel/NeoGeo_MiSTer) by [Furrtek](https://www.patreon.com/furrtek/posts)

Ported to MiST by Gyorgy Szombathelyi [(source code here)](https://github.com/gyurco/NeoGeo_FPGA)

Ported to Turbo Chameleon 64 by A. M. Robinson [(source code here)](https://github.com/robinsonb5/NeoGeo_FPGA)


## Limitations
The original Neo Geo system has big RAM/ROM memories, which don't fit into the BRAM of the MiST's FPGA. A new SDRAM controller was written, which can
read one 64 bit and one 32 bit word simultaneously in just 12 cycles using bank interleaving, and running at 120MHz. Later on, it was replaced by
a 96MHz variant reading two 32 bit words in 8 cycles. Both 32MiB and 64MiB equipped MiSTs are supported, the later obviously can load more games.

The limitation of ROM sizes for both variants:

**32 MiB** (original MiST and Turbo Chameleon 64) - supports  ~6 MiB PROMS and 24 MiB CROM+VROMs (in any size combination)

**64 MiB** - supports ~14 MiB PROMS and 48 MiB CROM+VROMs (in any size combination. Note: PROM size is not a real limitiation in this case.)

## Usage

Internal ROMs (System ROM, SFIX, LO ROM and SM1 ROM) can be created from MAME's neogeo.zip with the help of the [MRA files](https://github.com/mist-devel/mist-board/wiki/CoreDocArcade#mra-and-arc-files).
For convenience a copy of the .mra file is included.

TerraOnion .NEO file format was choosen as the supported cart format, as it conveniently merges all the various ROMs in one file. The following utilities can be used to create such files:

[Original NeoBuilder tool](https://wiki.terraonion.com/index.php/Neobuilder_Guide)

[Darksoft to .neo conversion tool](https://gitlab.com/loic.petit/darksoft-to-neosd/)

(For convenience a copy of the darksoft-to-neosd tool is included, but since it's written in Python you will need a working Python installation to use it.)

[MAME to .neo conversion tool](https://github.com/city41/neosdconv) - please note many MAME Neo Geo ROMs are encrypted, and these are not supported by the core, so it's recommended to use the Darksoft collection instead.


## Controls

The NeoGeo has four fire buttons, as well as start and select buttons - and in Arcade configurations there are coin buttons too.
On the TC64 the PS/2 keyboard, C64 keyboard and CDTV control pad are all supported.

Gamepad 1
~~~~~~~~~
| Gamepad button | PS/2 keyboard | C64 keyboard | CDTV controller |
| :------------- | :------------ | :----------- | :-------------- |
| A              | Right Ctrl    | N / Period   | Button A        |
| B              | Right Alt     | B / Slash    | Button B        |
| C              | Right Win     | Comma        | Vol Up          |
| D              | Slash         | Equals       | Fast Fwd        |
| Start          | Enter         | Return       | Play/Pause      |
| Select         | Right Shift   | M            | Vol Down        |

Directions on the C64 keyboard are mapped to I, J, K, L and the cursor keys.


Gamepad 2
~~~~~~~~~
| Gamepad button | PS/2 keyboard | C64 keyboard | CDTV controller |
| :------------- | :------------ | :----------- | :-------------- |
| A              | Left Ctrl     | C            | Button A        |
| B              | Left Alt      | V            | Button B        |
| C              | Left Win      | Z            | Vol Up          |
| D              | Z             | X            | Vol Down        |
| Start          | Enter         | Control      | Play/Pause      |
| Select         | Left Shift    | Run/Stop     | Fast Fwd        |

Directions on the C64 keyboard are mapped to W, A, S and D.


Mouse (trackball) support for the game Irritating Maze can be selected in the OSD. Middle mouse button is Start. **Note:** this game requires its own system BIOS.

## Memory Card

A 8K (8192 bytes) empty file can be used as a memory card. It can be loaded-unloaded and saved via the OSD (use a .SAV extension). Hint: rename it to **NeoGeo.vhd** and it'll be auto-mounted. One memory card
can store progress and high score information for a couple of games.

## Sidenotes (from Gyorgy):

The upstream MiSTer core was inherently unstable. While Furrtek (Sean Gonsalves) did a very good and tedious job reverse-engineering and documenting the original Neo-Geo chipset,
the resulting HDL is not very good for FPGAs. Probably MiSTer's Cyclone V FPGA can deal with it better, as it's built in a newer process, has smaller inner delays, has more clock networks,
or the more recent Quartus tool is better synthesizing such code, but it still broken. Translating old ASIC designs 1-1 into FPGA won't work, as there are dozens of generated signals
(even with combinatorial output) used as clocks, which are glitching, the compiler cannot check if flip-flops clocked by these signals meet setup and hold times, resulting
in very unstable cores.

At the end, the core's HDL was converted into synchronous code, using a simulator to check if it still produces the same signals as before. Finally all latches were eliminated,
and all generated clock usages were removed.

Thanks to all who supported this conversion!

