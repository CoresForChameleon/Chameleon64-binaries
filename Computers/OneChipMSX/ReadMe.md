# OneChipMSX Quick Start

To get the best from the OneChipMSX core, you will need an SD card (as opposed to an SDHC card), which should be FAT16 formatted.

It’s possible to load the BIOS from a FAT32-formatted SDHC card, but you’ll only be able to boot into BASIC – MSX-DOS itself requires FAT16 and non-SDHC.

## Formatting the card

If you have an SD card and need to format it as FAT16 you may find your operating system isn’t much help.  Windows users will find the SD Association’s formatting utility useful here:  https://www.sdcard.org/downloads/formatter_4/

## Adding the BIOS

The original OneChipMSX firmware could load the BIOS from SD card – but only if it was the first file in the filesystem.  This limitation is no longer present on my port of the core, since I’ve replaced the Initial Program Loader with the new Control CPU which handles the OnScreenDisplay as well as loading the firmware.

The BIOS can be found alongside [Caro’s DE0 or DE1 ports:](http://caro.su/msx/ocm_de1.htm).  Either the MSX3 or MSX2+ BIOS can be used – the firmware will attempt to use the MSX3 BIOS in preference, and fall back if necessary.

Alternatively, there is a .rar file at [http://www.msxpro.com/de0.html](http://www.msxpro.com/de0.html) which contains everything you need to boot OneChipMSX – MSX2+ BIOS, operating system and ROMLoad.

## The Operating System

To run MSX DOS you will need two more files on your SD card: MSXDOS2.SYS and COMMAND2.COM   These can be found in the .rar file on the page linked above

Just like MS DOS you can use an autoexec.bat file to run comands at startup, and the command set will feel familiar to MS DOS users.  It even has tab completion!

## Loading a ROM Image

Cartridge images can be stored on the SD Card, either loose or in subdirectories.  Long filenames are not supported, so it’s a good idea to rename them to something within the standard 8.3 format, otherwise you’ll have to contend with confusing “prefix~1.ext” style filenames.  Once your SD card contains suitable ROMs, they can be launched from the command line like so:

	A:\> romload path\to\file.rom

This command will load a ROM image into one of the emulated memory expansions (assuming they’re enabled) but won’t actually launch it.  To launch it, either reset the core, type “reset” at the command line, or supply the /r switch after the filename when invoking romload.

A nice selection of Konami ROMs can be found here: www.msxarchive.nl/pub/msx/games/roms/konamigames.zip

## Using Disk Images

The OneChipMSX has support for mounting disk images, using the EP command – if you don’t have this, it can be found as part of this archive: http://msxbanzai.tni.nl/computers/ese3.zip  (This is the software that came with the “real” OneChipMSX – the tools you need are in the Tools subdirectory.)

To mount a disk image, use the following command:

	A:\> ep image.dsk b:

Now you can address the disk as drive B:\.

Alternatively, the following command will mount and auto-boot from the disk:

	A:\> ep image.dsk /b /r
 

(Thanks to users jugac64 and fierman from the chameleon_64 Yahoo group for their contributions to this guide.)

Source code for this core can be found at [https://github.com/robinsonb5/OneChipMSX](https://github.com/robinsonb5/OneChipMSX)

