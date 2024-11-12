Pacman hardware FPGA core, ported to Turbo Chameleon 64 from MiST]
by Alastair M. Robinson

This core supports multiple games, all based on the PacMan hardware.
MAME ROM files and associated .arc files are are required, and not
distributed with the core for copyright reasons.  The ROMs must be
converted into the correct format using each game's .mra file.  This
is processed using the mra-tools-c package which can be found at
https://github.com/mist-devel/mra-tools-c
(You don't have to build it from source - there are binaries for
both Linux and Windows in the release directory.)

Mra files for the supported games can be found in the "meta" directory.

The .arc file for each game contains the ROM filename as well as details of
any DIP switches the game supports, so when loading a game you should select
its .arc file from the file selector, instead of the .rom file.

When converting the ROM using mra-tools, you should supply the "-A" argument
to request that the .arc file be generated, like so:

> ./mra -A <game>.mra

Keys follow the MAME pattern, with keys "5" to "8" inserting coins and "1"
through "4" being player 1 through 4's start buttons, respectively.

PS/2 keyboard, C64 keyboard, joystick and CDTV pad are all supported.

Please note, Pacman hardware uses a monitor in portrait format, and this core
does the same.  This version of the core is capable of rotating and scaling
the game's playfield to fit a landscape format monitor, or you can run the 
core rotated if you have a monitor which can run in portrait format.
Screen orientation can be selected from the OSD - but please note that the new
"vertical" mode, in which the screen is rotated and scaled, only works when
the scandoubler is enabled.


Have fun!



Original README follows:

-- A simulation model of Pacman hardware
-- Copyright (c) MikeJ - January 2006
--
-- All rights reserved
--
-- Redistribution and use in source and synthezised forms, with or without
-- modification, are permitted provided that the following conditions are met:
--
-- Redistributions of source code must retain the above copyright notice,
-- this list of conditions and the following disclaimer.
--
-- Redistributions in synthesized form must reproduce the above copyright
-- notice, this list of conditions and the following disclaimer in the
-- documentation and/or other materials provided with the distribution.
--
-- Neither the name of the author nor the names of other contributors may
-- be used to endorse or promote products derived from this software without
-- specific prior written permission.
--
-- THIS CODE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
-- AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO,
-- THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR
-- PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE AUTHOR OR CONTRIBUTORS BE
-- LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR
-- CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF
-- SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS
-- INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN
-- CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE)
-- ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE
-- POSSIBILITY OF SUCH DAMAGE.
--
-- You are responsible for any legal issues arising from your use of this code.
--
-- The latest version of this file can be found at: www.fpgaarcade.com
--
-- Email pacman@fpgaarcade.com
--
-- Revision list
--
-- version 006 Merge different variants by Alexey Melnikov
-- version 005 Papilio release by Jack Gassett
-- version 004 spartan3e release
-- version 003 Jan 2006 release, general tidy up
-- version 002 optional vga scan doubler
-- version 001 initial release
