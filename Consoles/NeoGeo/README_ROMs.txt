Please note: Both the BIOS and the individual game ROMs are copyrighted, and
the property of their respective owners, and the standard disclaimers about
downloading ROMs of games you don't own being copyright infringement apply
here.


# BIOS

A BIOS file, named "neogeo.rom" is required for the Neo Geo core.  This can
be generated from MAME Neo Geo BIOS ROMs using the mra-tools utility which
can be found at https://github.com/mist-devel/mra-tools-c
(You will have used this already if you've experimented with any of the
previously-ported arcade cores.)

The BIOS directory contains three .mra files - one of them is for a specific 
game, one of them is for the European NeoGeo console, and the Universe Bios
is a hack which can be used with the core in both arcade and console mode,
so this is recommended.

You will need a neogeo.zip file from a MAME ROM set.  The easiest way to
obtain this is to search on Archive.org for "NeoGeo Starter" - the 
[MiSTerFPGA] NeoGeo MVS Starter Pack contains many files, most of which we
don't want, so don't download the whole thing - instead just click "Show all",
then you can download just the neogeo.zip file.

Having downloaded neogeo.zip, put it in the same directory as the .mra files
and use the mra utility like so:
> /path/to/mra UniverseBIOS_Hack_Ver40.mra
This command should produce a neogeo.rom file which you can copy to your SD
card.


# Obtaining and converting ROMs.

The NeoGeo core is best used with the DarkSoft ROM collection, but the ROMs
have to be converted to TerraOnion .neo format before they can be used.

At the time of writing a search on Archive.org for "Neo Geo Darksoft" will 
find a collection of ROMs that have already been converted.

Failing that, a darksoft_to_neosd conversion utility is included - however
it's written in python so will need a working python installation to use it,
like so:
> python convert.py /path/to/darksoft_collection/games /output/directory

There are other ways to convert the ROMs, too - including a GUI-based tool for
Windows which can be found at wiki.terraonion.com/index.php/Neobuilder_Guide


Please note, due to the limited RAM availble on the Turbo Chameleon 64, only a
subset of the NeoGeo game catalogue can be played.  Some can be played, even
if they don't fit, but with corrupted graphics.  Yet others will fit, with
compromised sound, if you use the "Load Cart (skip ADPCM)" menu option to load
a game.


