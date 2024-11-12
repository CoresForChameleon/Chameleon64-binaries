# Apple //e for Turbo Chameleon 64, ported from MiST.

Supports C64 keyboard and joystick (mapping digital joysticks to emulated analogue joysticks)

Supports emulation of 2 disk drives
Please note: disk images must be converted to .nib format.  A utility, dsk2nib, is provided
to perform this task.  dsk2nib is supplied as pre-compiled Windows executable and with C
source code which should compile easily for other platforms.



# Original documentation follows:

The MiST port is based on of a reconstruction of an 1980s-era Apple //e (enhanced) implemented in VHDL for FPGAs.
The project based on an Apple ][+ FPGA implementation.
Original for the DE2: http://www1.cs.columbia.edu/~sedwards/apple2fpga/
Port for the MiST: http://ws0.org/tag/apple2/

Features:
- Disk .NIB file selection via OSD (read/write)
- Tape loading via the UART RX pin
- Selectable 6502 or 65C02 CPU
- Joystick support
- RGB (optionally scandoubled for VGA) or YPbPr output
- Color, amber, green and black&white monitor
- 64K base + 64K auxilary RAM with 80 column and double hi-res support
- Mockingboard model A (two AY-3-8913 chips for six audio channels) in slot 4

On the "Apple //e" boot screen open the OSD with F12 and choose a nibblelized disk. It will boot
the disk automatically. Use dsk2nib to convert AppleII disk images to .nib images. 
The disk emulation is read only.

If you press reset (the right button on the MiST) you'll enter Applesoft with the ] prompt.
From here you have the Applesoft BASIC. See: http://www.landsnail.com/a2ref.htm
If you want to boot another disk choose a .nib image via the osd and type the following:

]PR#6

or

]CALL -151
*C600G

The call command will enter the Monitor. Type the call a second time if the * prompt won't
show the first time. 
At the Monitor you can also type 6 and then Ctrl-P followed by return.
See http://vectronicsappleworld.com/appleii/dos.html#bootdos
