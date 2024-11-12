Plus Too for the Turbo Chameleon 64
===================================

This is a port of the [Plus Too project](http://www.bigmessowires.com/plus-too/) to the 
Turbo Chameleon 64.

Usage
-----

- Copy a Mac Plus rom onto the SD card under the name plus_too.rom
  a suitable ROM can be found at https://github.com/ManuFerHi/SiDi-FPGA/tree/master/Cores/Computer/Plus_too

- Copy disk images in dsk format onto the SD card

A few seconds after booting the core, the floppy disk icon should appear.
Open the on screen display using the F12 key and select a disk image.
The upload of the disk image will take a few seconds. Plus Too will then boot into the MacOS desktop.


Floppy disk image format
------------------------

Floppy disk images are supported by uploading them into RAM. This means that changes made to the disk won't be saved
to the image file on the SD card - so floppy disks should currently be considered read-only.

Floppy disk images need to be in raw disk format. Double sided 800k disk images have to be exactly
819200 bytes in size. Single sided 400k disk images have to be exactly 409600 bytes in size.

Both the internal as well as the external floppy disk are supported. The first entry in the OSD refers
to the internal floppy disk, the second one to the external floppy disk.

Currently floppy disk images cannot be uploaded while the Mac accesses a floppy disk. Thus it's
recommended to wait for the desktop to appear until a second floppy can be inserted.

Before uploading a different disk image it's recommended to eject the previously inserted disk image from within MacOS.

Some system floppy disk images in matching dsk format used to be available at http://www.rolli.ch/MacPlus/welcome.html
While that site is now defunct, the files can still be accessed via the Wayback Machine at archive.org.
There's also a set of 800k system disk images for MacOS 6.0.8 at archive.org - the files just need renaming from
.img to .dsk


Hard disk support
-----------------

This Plus Too core implements the SCSI interface of the Macintosh Plus together with a 20MB harddisk.
The core implements only a subset of the SCSI commands. This is currently sufficient to read and write the disk,
to boot from it and to format it using the setup tools that come with MacOS 6.0.8.

Harddisk images can be attached to one of four SCSI units using the OSD menu.
The format of the disk image is the same as being used by the SCSI2SD project which is documented 
at http://www.codesrc.com/mediawiki/index.php?title=HFSFromScratch

Unlike the floppy the SCSI disk is writable and data can be written to the disk from within the core.

It has been tested that OS 6.0.8 can format the SCSI disk as well as doing a full installation from floppy disk
to the harddisk. But keep in mind that this is an early work in progress and expect data loss when working with HDD images.

A suitable blank harddisk image file can be found at https://github.com/mist-devel/mist-binaries/raw/master/cores/plus_too/hdd_empty.zip
This is a 20MB harddisk image with correct partitioning information and a basic SCSI driver installed. The data partition itself is empty
and unformatted. After booting the Mac will thus ask whether the disk is to be initialized.
Saying yes and giving the disk a name will result im a usable file system. You don't need to use the Setup tool to format this disk as 
it is already formatted. But you can format it if you want to. This is only been tested with OS 6.0.8.


Configuration Files
~~~~~~~~~~~~~~~~~~~
With the On-Screen Display open, press the cursor-right key to switch to the Configuration File menu.
From here you can load and save configuration files, which contain hard disk image paths and names, as well as other
core settings, and also the emulated Mac's PRAM.  The floppy disk image filenames are not saved, however.

The menu firmware isn't able to create new files, but an example file is provided, so copy this to the SD card and add extra
copies if you wish.


CPU Speed
---------

The CPU speed can be adjusted from "normal" which is roughly Mac Plus speed to "Fast" which is about 2.5 times faster. Two CPU cores
are provided, FX68K is a cycle-accurate 68000 core, TG68K 68010/68020 core.

