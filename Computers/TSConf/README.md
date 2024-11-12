# TSConf for MiST FPGA computer

This is the port of TSConf (advanced ZX Spectrum-compatible platform) to Turbo Chameleon 64
based on Eugene Lozovoy's port to [MiST](https://github.com/mist-devel/mist-board)
and [MiST.1010](https://github.com/UzixLS/mist1010-board).


## Features of this port
- VDAC 1
- RTC
- ZiFi (WiFi)
- Tape in/out via UART_RX/UART_TX pins
- MIDI output via UART_TX pin
- TurboSound FM (2x YM2203)
- General Sound 2MB
- SAA1099
- Covox
- SounDrive
- 2x Kempston/Sinclair/Cursor joystick
- Kempston mouse


## TSConf features
- High compatibility with original Pentagon-128 clone
- Advanced video features:
  - Pixel resolutions 360x288, 320x240, 320x200, 256x192
  - Up to 720x288 Hi-res pixel resolution
  - Hardware scrolled graphic planes
  - 256 and 16 indexed colors per pixel
  - Programmable color RAM with RGB555 color space and 256 cells
  - 512 and 256 bytes per line addressing
  - Text mode with loadable font and hardware vertical scroll
  - Up to 256 graphic screens
- Hardware engine for Tiles and Sprites graphics
  - Up to 85 sprites per line
  - Sprites sized from 8x8 to 64x64 pixels
  - Up to 3 sprite planes
  - Up to 2 tile planes with 8x8 pixels tiles
  - Up to 16 palettes for sprites per line
  - Up to 4 palettes for tiles per line for each tile plane
- Z80 Memory addressing enhancements:
  - Programmable RAM page for any 16kB window
- Z80 acceleration features
  - Selectable CPU clock 14MHz, 7MHz and 3,5MHz
  - 512 bytes of zero-wait RAM for 14MHz
  - On-the-fly programmable maskable interrupt position
  - Separate IM2 vectors for different interrupt sources
- Advanced hardware features
  - DRAM-to-Device, Device-to-DRAM and DRAM-to-DRAM DMA Controller

See details in the official git repository: [link](https://github.com/tslabs/zx-evo/blob/master/pentevo/docs/TSconf/tsconf_en.md)


## Installation
Place TSConf.ROM and TSConf.R01 files from [release](https://github.com/mist-devel/mist-binaries/tree/master/cores/tsconf) into root of SD card.

At the same place you can find an example TSConf.VHD file with Wild Commander installed, but little else.
The easiest way to use the core will be to put Wild Command in the root of your SD card along with some games and demos.


## Usage
Because we use F12 for the menu on nearly all cores, the original TSConf F12 key (reset) is transferred to F11 instead.
On the C64 keyboard (which has no F11 key), hold Run/Stop and press F7/F8 instead.
To enter the TS-BIOS setup utility, press Right Shift + F11 (or Run/Stop + Right Shift + F7/F8 on the C64 keyboard).
In the BIOS setup utility you can choose what happens at two different types of reset:
The first occurs when you just press F11
The second occurs when you press Left Shift + F11
Typically, one type of reset will boot to BASIC, like a regular ZX Spectrum, and the other will boot from SD card or disk image.

The BIOS settings are stored in NVRAM which can be saved as part of a config file.  A few example configs are supplied, and can be
loaded by entering the OSD menu and pressing cursor-right to access the load/save settings menu.
If you want a config file to be used by default, just rename it to "TSConf.cfg" and place it in the root of the SD card.


## Software
- Wild Commander: https://forum.tslabs.info/viewtopic.php?f=26&t=143
- ZiFi: http://zifi.vtrd.in/
- Demos and games: https://prods.tslabs.info/


## Credits
- TSConf official git repository - [link](https://github.com/tslabs/zx-evo/tree/master)
- TSConf official forum - [link](http://forum.tslabs.info/viewforum.php?f=20&sid=137db6b31f9fb533b908742c2b18284e)
- Original TSConf port for MiSTer (on base of which this port was created) - [link](https://github.com/MiSTer-devel/TSConf_MiSTer)
- T80 - Z80 HDL implementation
- JT12 - Yamaha OPN HDL implementation - [link](https://github.com/jotego/jt12)
- Source for this port - [link](https://github.com/robinsonb5/TSConf_DeMiSTify)


