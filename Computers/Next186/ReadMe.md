# Next186

By Nicolae Dumitrache (https://opencores.org/projects/next186_soc_pc)

[JTOPL](https://github.com/jotego/jtopl) by Jose Tejada (@topapate)

[A VHDL 16550 UART core](https://opencores.org/projects/a_vhd_16550_uart) Copyright (c) 2006 by H LeFevre

SN76489AN Compatible Implementation in VHDL Copyright (c) 2005, 2006, Arnim Laeuger (arnim.laeuger@gmx.net)

Port to MiST, CGA modes, VGA, PIT, PIC improvements by Gyorgy Szombathelyi

Preliminary and experimental port to Turbo Chameleon 64 using the DeMiSTify framework
by Alastair M. Robinson

## Usage and limitations of the DeMiSTify port

At present the DeMiSTify core only supports a single hard drive image, which must be stored on the SD card
under the name "Next186.VHD".
The card must also contain the BIOS, under the name Next186.ROM
If a "Next186" directory exists on the SD card, the BIOS and hard disk image will be loaded from there,
otherwise they will come from the root directory.

Most of the infrastructure is in place to support two emulated IDE hard drives, however there's currently
no way to mount those drives, and they would require a suitable IDE driver to be installed under DOS
since the BIOS can't currently talk to IDE devices directly.

Note, too, that unlike the previous experimental port to Turbo Chameleon 64 (which had no on-screen display)
this version can't currently access the SD card directly.

The upstream Next186 core includes an optional Digital Signal Processor but this is currently disabled in
order to make the core fit the TC64's resources.

Source code can be found at https://github.com/robinsonb5/Next186_DeMiSTify

