Acorn Archimedes core for Turbo Chameleon 64
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Original core by Stephen J. Leary, with enhancements
by Gyorgy Szombathelyi
DeMiSTified by Alastair M. Robinson


Currently supported:
~~~~~~~~~~~~~~~~~~~~
* Floppy disk images
* Hard disk images
* CMOS RAM
* Keyboard (PS/2 and C64)
* Mouse (PS/2)
* Configuration files


ROM
~~~
The core requires a RiscOS ROM file on the SD card, and this must be named
"RISCOS.ROM" (unless specified otherwise in a configuration file).
The highest supported RiscOS version is 3.11 (English), or 3.19 (German)

You can load alternative ROM versions from the OSD, but since the core won't
produce any video until at least one ROM has been loaded, you do need a
default ROM on the SD card.


CMOS RAM files
~~~~~~~~~~~~~~
The Archimedes contained some battery-backed CMOS RAM for configuration data
and this is emulated with a file on the SD card, named CMOS.RAM by default.
Three versions of this file are provided, all with IDE hard disk enabled but
with different monitor settings.  Copy one of them to the SD card (and if you
don't want to use a configuration file, rename it to CMOS.RAM if necessary):

* CMOS.RAM sets the monitor type to multiscan, which allows higher resolutions
  for the desktop, and allows games to open a 50Hz PAL-compatible display
  (scandoubled by defaults).

* SVGAIDE.RAM sets the monitor type to SVGA, which will enable higher resolutions
  for the desktop but will prevent games from opening a 50Hz display, which will
  give odd looking results.

* 15KHzIDE.RAM sets the monitor type to "normal", i.e. 15KHz/50Hz PAL.
  In combination with a configuration file which disables the scandoubler, this
  should make the core compatible with monitors which can only handle 15KHz.


Configuration files
~~~~~~~~~~~~~~~~~~~
The on-screen menu has a second page, accessed by pressing cursor-right, from which
configuration files can be loaded and saved.  The files store the directory and filename
of the currently loaded ROM and currently mounted hard disk images, as well as the status
of the scandoubler.
As with other DeMiSTified cores, the core can't create new configurations, only overwrite
existing ones.  Two examples are provided - Archimed.cfg and Archimed_15KHz.  Copy one of
these to the root of the SD card, and rename it to Archimed.cfg if necessary.  (The only
difference between the two files is that the latter has the scandoubler disabled, for use
with the 15KHzIDE.RAM file.


HDF files
~~~~~~~~~
You can find an example HDF file here:
https://github.com/mist-devel/mist-binaries/tree/master/cores/archimedes
You can mount this file using the menu.  At bootup the core will attempt
to mount automatically a file named "archie1.hdf" (or an alternative name
if specified in a configuration file.)


Keyboard handling
~~~~~~~~~~~~~~~~~
The C64 keyboard has fewer keys than a real Archimedes keyboard so there's
some "creative" mapping in use.  The most important keys are F12 (used by the
Archimedes) and PrintScreen (used by the core as a menu button.)
* The run/stop key on a the C64 keyboard is used as a modifier, similar to the
Fn key on a laptop.
* The F12 key is mapped to run/stop-del on the C64 keyboard.
* The Commodore key is mapped to Left Alt.


Other keys
~~~~~~~~~~
| Function        | PS/2 keyboard | C64 keyboard  | CDTV controller |
| :-------------- | :------------ | :------------ | :-------------- |
| Menu            | Prt Screen    | Run/stop - <- | Power           |


Known problems
~~~~~~~~~~~~~~
At bootup the core will pause for several seconds with a red border and with
red LED on the Chameleon blinking. I haven't yet figured out the reason for
this.

The shift keys sometimes appears to get stuck, either in the on or off
position.


Source code for this core can be found at
https://github.com/robinsonb5/archimedes

The core is a port of original work by Mike Sterling with major changes by 
Stephen Leary and David Banks, and further improvements by Gyorgy Szombathelyi
and Till Harbaum.

The Turbo Chameleon 64 port wraps the MiST core in a compatibility layer
(DeMiSTify, by Alastair M. Robinson) and with a few tweaks to reduce the
block RAM usage, and leave room for the DeMiSTify ROM.

