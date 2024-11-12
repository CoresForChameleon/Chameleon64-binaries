# SAM Coupe FPGA core
by Alexey Melnikov
Ported to Turbo Chameleon 64 by Alastair M. Robinson

### Features:
- Fully functional SAM Coupe with precise CPU and Video timings.
- Real CPU frequency for ZX mode and full speed (6MHz) for other modes.
- Turbo up to 24MHz
- 512KB of original internal memory.
- Emulation for 4MB of extended memory.
- Two disk drives.
- Support for disk formats: EDSK, MGT, IMG.
- Write support.
- Original SAM joysticks (same as Sinclair 1 and 2).
- Kempston joystick (useful for some ZX games).
- SAA1099 sound chip.
- SID MOS6581 sound chip.
- Stereo SAM DAC on LPT1.
- Mouse.


### Installation:
Flash the .rbf file to your Turbo Chameleon 64 using Chaco.
You will need ROM file in the root directory of your SD card,
called SAMCoupe.ROM. A suitable file can be found at
https://github.com/sorgelig/SAMCoupe_MIST/tree/master/releases


### Notes about supported disk formats:
**MGT** is simple sector dump of SAM disks. All disks have the same size
819200 (for 80 track disks).

**IMG** is the same as **MGT** but uses different layout. It's used on +D FDC
add-on (ZX Spectrum).

**EDSK** is format for non-standard disks. Sizes up to 1024kb are supported.
There is only basic support for EDSK format. If application has strong copy
protection then it may not work.

**MGT and EDSK formats may have common file extension - DSK. IMG format should 
use extension IMG for correct detection**.

Other formats like **SAD,SDF,TD0, etc.** can be converted to one of the
supported formats using SAMdisk, which can be found at
http://simonowen.com/samdisk/

Writing to disk isn't mature, so be sure to make a backup of any important
 disk images before write to them.

The core provides autostart for newly inserted disk into drive 1. Autostart
works only on the startup screen with stripes.
Press any key after restart before loading the disk if you don't want
autostart.

### Keyboard:
Most PC keys are mapped to the same SAM Coupe keys.
**F1-F10** mapped to **F1-F0**,
**Alt** is mapped to **Symbol shift**.
**Left Shift** is mapped to **Shift**, 
**Right Shift** doesn't map to SAM Coupe key but used as modifier for
unfitted keys to represent original SAM Coupe keys. For example RShift + 6...0
prodice keys as written on PC keyboards. Suitable for other close to RShift PC
keys. 
**RShift+Ctrl** switches to layout more suitable for ZX (where cursor keys are
mapped to CAPS 5-8) although most SAM Coupe ZX emulators already provide good
mapping and thus usually you don't need to switch layout.

* F11 - NMI key
* Ctrl-F11 - reset.
* Alt-F11 - reset and unload disk images.
* F12 - show OSD

### Other info:
**CPU Speed** modes:
- Normal - original SAM coupe 6MHz clock with wait states
  (full 6MHz while accessing extended RAM).
- 6MHz - full 6MHz speed without wait states.
- 9.6MHz, 12MHz, 24MHz - turbo modes.

**ZX mode speed**:
- Emulated - original SAM Coupe ZX CPU emulation (through wait states).
- Full - full SAM Coupe CPU clock.
- Real - original ZX CPU clock (3.5MHz).

*Note 1*: Real mode is useful for ZX import where beeper used for sound.
In emulation and full modes the sound is garbled in such games while real
frequency provides clean sound. (Arkanoid 48k is a good example).

*Note2*: Emulated mode is true only for Normal CPU speed. For other
CPU speeds this value equals to Full speed.

**External RAM** enables/disables support for additional 4MB of RAM.
Disabling external RAM reduces startup time of some apps. Some apps can
gain advantages if this option is enabled.
Actual change of this option happens upon reset.


Source code for the core can be found at 
https://github.com/robinsonb5/SAMCoupe_DeMiSTify

