# [IBM PC/XT](https://en.wikipedia.org/wiki/IBM_Personal_Computer_XT) for [MiST](https://github.com/mist-devel) and [DeMiSTify](https://github.com/robinsonb5/DeMiSTify)

MiST and DeMiSTified ports by [@somhi](https://github.com/somhi) from original PCXT port for [MiSTer FPGA](https://mister-devel.github.io/MkDocs_MiSTer/) by [@spark2k06](https://github.com/spark2k06/) (https://github.com/MiSTer-devel/PCXT_MiSTer).

Follow discussion and evolution of the core at [MiSTerFPGA forum](https://misterfpga.org/viewforum.php?f=40) and [MiST Atari-forum](https://atari-forum.com/viewtopic.php?t=42465).

Ported to Turbo Chameleon 64 by Alastair M. Robinson

**Status of the port** 

This core is designed to support multiple target platforms, not all of which
have a large enough FPGA to support all features.

The TC64 port implements the following:

* Support for IBM PCXT 5160 and clones

* Support for Tandy 1000 (with suitable BIOS)

* 8088 CPU at 4.77 MHz, 7.16 MHz, 9.54 MHz cycle accurate, and PC/AT 286 at 3.5MHz equivalent (max. speed)

* BIOS selectable (Tandy 1000 / PCXT). Compatible BIOS selection (IBM5160, Yuko ST, pcxt31, Tandy, micro8088, XT-IDE, ...)

* XT-IDE support

* Main memory 640Kb + 384Kb UMB memory

* EMS memory up to 2Mb

* Video modes (VGA or RGB 15 kHz)
  * CGA graphics 32kB VRAM
  * Tandy graphics, limited to 32Kb of RAM due to size constraints on TC64
  
* Audio: Tandy, Speaker

* Joystick support

* C64 keyboard support

* PS/2 Mouse bridged into COM2 serial port, this works like any Microsoft mouse.
You just need a driver to configure it, like CTMOUSE 1.9 (available into hdd folder),
with the command CTMOUSE /s2 

* Configuration files which bundle up a selection of BIOS ROMs and hard disk images.


Due to space constraints there is no support on TC64 for the following:

* MDA video

* Adlib sound

* Gameblaster Sound


Please note: While IDE hard disk images are supported, there is no support
for floppy disk images.


## **Quick Start**

* BIOS: A free BIOS image is supplied, which should be copied to the SD card. 
It should be named PCXT.ROM
This BIOS file is `pcxt_pcxt31.rom`: ([Source Code](https://github.com/virtualxt/pcxtbios))
While this BIOS is enough to get started, see the BIOS section below for
more complete information about BIOSes.

* Hard drive image - a FreeDOS image which contains some scene demos can be found at [hd_image.zip](https://github.com/MiSTer-devel/PCXT_MiSTer/raw/main/games/PCXT/hd_image.zip) - this should be uncompressed and copied to the SD card.
If you name the file "PCXT1.VHD" and store it in the card's root directory, it will be automatically mounted at boot.

* Configuration File - at boot time the core will attempt to load a configuration file named PCXT.CFG, from which it will take the filename and
containing directory of the BIOS ROMs and hard disk images.
As with other DeMiSTified cores, the core is unable to create new files, so instead copy the example configuration file provided onto the SD card
and overwrite it with your own settings.
Menu options to load and save configuration files are on a second page of the on-screen menu, accessed by pressing cursor-right when the menu is open.


## Description

The purpose of this core is to implement a PCXT as reliable as possible. For this purpose, the [MCL86 core](https://github.com/MicroCoreLabs/Projects/tree/master/MCL86) from [@MicroCoreLabs](https://github.com/MicroCoreLabs/) and [KFPC-XT](https://github.com/kitune-san/KFPC-XT) from [@kitune-san](https://github.com/kitune-san) are used.

The [Graphics Gremlin project](https://github.com/schlae/graphics-gremlin) from TubeTimeUS ([@schlae](https://github.com/schlae)) for CGA and MDA video output.

[JTOPL](https://github.com/jotego/jtopl) by Jose Tejada (@jotego) was integrated for AdLib sound.

[JT89](https://github.com/jotego/jt89) by Jose Tejada (@jotego) was integrated for Tandy sound.

[MiST](https://github.com/mist-devel) modules is used for MiST and DeMiSTified ports. Specials thanks to [@Gyurco](https://github.com/Gyurco) for helping adding IDE support in MiST ports.

[Demistify](https://github.com/robinsonb5/DeMiSTify) by Alastair M.Robinson ([@robinsonb5](https://github.com/robinsonb5)) is used as a MiST compatible framework using a softcore for aiding porting the core to multiple FPGA boards. More information about deMiSTifying a core can be found on this [tutorial](https://github.com/DECAfpga/DECA_board/tree/main/Tutorials/DeMiSTify). 
  

## Quick Start

* Download and uncompress [hd_image.zip](https://github.com/MiSTer-devel/PCXT_MiSTer/raw/main/games/PCXT/hd_image.zip)  on your host system (it contains a [freedos](http://www.freedos.org/ ) image)
* Prepare an SD card for your FPGA 
  * MiST ports: rename previous image to PCXT.HD0 (primary IDE). Secondary IDE disk will be loaded if PCXT.HD1 file is present.
  * DeMiSTify ports: rename previous image to PCXT1.VHD (primary IDE). Secondary IDE disk will be loaded if PCXT2.VHD file is present.
  * Create also a PCXT folder containing all the BIOSes  (see ROM instructions below). 

* Load (or flash) PCXT core with the SD card inserted and press F12 on your keyboard to access the OSD to select options:
  * Model:  IBM PCXT (Note: for Tandy is needed to generate the Tandy BIOS first)
  * CPU Speed: 4.77MHz for better compatibility (PC/AT 3.5MHz for max. speed)
  * BIOS > PCXT BIOS > browse to the BIOS folder and choose e.g. pcxt_pcxt31.rom. For automatic load of BIOSes read section below.
  * Mount IDE: only for DeMiSTify ports select in OSD the VHD or IMG image for primary / secondary IDE HD and Reset core.
* To load floppies it is only possible with an USB serial cable connected to your Host computer using [Serdrive](SW/ ) as explained below at Mounting the disk image section. With this method it is possible to load HD images also. Press ALT key during boot to detect the COM drives.


## BIOS instructions

BIOSes can be selected in the BIOS section of the OSD menu. After selecting each BIOS a reset is done. 

Automatically load of BIOS is possible by leaving the BIOS files into the root of the SD card with the following names:

* PCXT.ROM  for the PCXT BIOS
* TANDY.ROM for the TANDY 1000 BIOS
* XTIDE.ROM for the XT-IDE BIOS (needed to load the OS, but already embedded in some ROMs)

(These filenames and containing directory can be overridden by a PCXT.CFG configuration file.)


## OSD Controls

* F12 show / hide OSD 
* DeMiSTified ports: Long F12 toggles VGA/RGB mode 

Some ROM-related files can be found at: https://github.com/somhi/PCXT_DeMiSTify/tree/main/SW/ROMs

Open Source ROMs are available here:

* `pcxt_pcxt31.rom`: This ROM already has the XTIDE BIOS embedded at address F000h. ([Source Code](https://github.com/virtualxt/pcxtbios))
* `pcxt_micro8088.rom`: This ROM already has the XTIDE BIOS embedded at address F000h. ([Source Code](https://github.com/skiselev/8088_bios))
* `ide_xtl.rom`: This ROM corresponds to the XTIDE BIOS, it must be maintained for some scripts to work, it can also be upgraded to a newer version. ([Source Code](https://www.xtideuniversalbios.org/))

The following python scripts can be used to download and generate ROMs:

* `make_rom_with_ibm5160.py`: A valid ROM is created for the PCXT model (pcxt.rom) based on the original IBM 5160 ROM, requires the XTIDE BIOS at address EC00h to work with HD images.
* `make_rom_with_jukost.py`: A valid ROM is created for the PCXT model (pcxt.rom) based on the original Juko ST ROM, and with the XTIDE BIOS embedded at address F000h.
* `make_rom_with_tandy.py`: A valid ROM is created for the Tandy model (tandy.rom) based on the original Tandy 1000 ROM, requires the XTIDE BIOS at address EC00h to work with HD images.

From the same BIOS section of the OSD it is possible to specify an XTIDE ROM of up to 16Kb to work at address EC00h. It is also provided in this folder (ide_xtl.rom).


NOTES:

* ROMs working with MDA video: (IBM5160, Yuko ST and pcxt31 work), (Tandy, micro8088, full XTIDE BIOS do not work). If you load a BIOS that does not work with MDA you may need to power cycle the board.

* IBM5160 BIOS: Starting BIOS at PC/AT 3.5MHz (max. speed), lights start blinking and keyboard doesn't work anymore. Starting BIOS at 4.77 MHz and changing it thereafter during the RAM test to PC/AT 3.5MHz (max. speed) it lets you work in this BIOS without keyboard problems.


