********************************************************************************

# uBee512

An emulator for the Microbee Z80 ROM, FDD and HDD based models.
Copyright (C) 2007-2016 uBee

For contact details please see the 'Contact' section at the end of this file.
********************************************************************************

# Distribution License
The GPL in this distribution applies to the uBee512 sources, and the
binaries produced from it.  The SDL, LibDsk, z80ex, zlib, zziplib and Mesa
components carry their own respective licenses.  The GPL does not apply to
any other parts of the distribution unless clearly stated.  Other files and
utility programs that are not GPL may form part of this distribution but
these are not required to be able to use the uBee512 emulator.

## uBee512 GPL
uBee512 - An emulator for the Microbee Z80 ROM, FDD and HDD based models.
Copyright (C) 2007-2016  uBee

This program is free software; you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation; either version 2 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program; if not, write to the Free Software
Foundation, Inc., 59 Temple Place, Suite 330, Boston, MA  02111-1307  USA

## uBee512 Tools License
These tools are "Freeware".  The software comes with absolutely no
warranties and are to be used at your own risk.  The code is provided
"as-is".

The source/scripts and binary code are allowed to be modified for personal
use only, these must not be used in any other projects in original or
modified form without written permission from the author.

# Third party software
- Z80Ex is the portable ZiLOG Z80 CPU emulator designed as a library.
  http://sourceforge.net/projects/z80ex/

- Simple DirectMedia Layer library by Sam Lantinga et al.
  http://www.libsdl.org/

- LibDsk by John Elliott.  LibDsk is a library intended to give transparent
  access to floppy drives and to the "disc image files" used by emulators to
  represent floppy drives.
  http://www.seasip.demon.co.uk/Unix/LibDsk/

- zziplib ZIP library for ZIP archives.  zziplib is distributed under the
  MPL and LGPL licenses.
  http://zziplib.sourceforge.net/

- zlib Compression Library.
  http://www.zlib.net/zlib_license.html
  http://www.zlib.net/

- Mesa 3-D graphics library.
  http://www.mesa3d.org/

# Overview
Welcome to the uBee512 Microbee emulator.

uBee512 is an emulator for the Microbee Z80 series of microcomputers. 
Emulation of all ROM, Floppy and Hard disk based models, including 512K and
2MB extended memory is supported.  The display may use SDL or OpenGL video
rendering.  Emulation includes Premium and Standard model graphics and
sound, Z80 PIO emulation of tape, sound, RTC, serial to PC RS232, printer,
BeeThoven, BeeTalker, DAC, Compumuse and Mouse peripherals support.  A wide
range of disk image types are supported as well as direct floppy disk
read/write.  A joystick may also be used and optionally mapped to keys.

The program is command line driven and provides many options.  An OSD GUI
interface is also provided and will have more features added as time
permits.

You can get the packages from here:
http://www.microbee-mspp.org.au/repository

This README file is updated for each new release and may contain additional
examples and corrections.

This project is a fork of the nanowasp v0.22 project and was started on the
5th June 2007.

## Objective
The objective of the emulator is to emulate all Z80 Microbee computer models
and to run existing software that works on a real Microbee and to support
all the standard and later the optional peripherals.

Third party variations and add-ons may also be added from time to time.

## Platforms
The source should be able to be built and run under most platforms that
supports SDL.  From version 4.0.0 on the z80ex Z80 emulator is now compiled
in as the default Z80 emulator.  This portable Z80 emulator is coded in 'C'
and should work on all Endian platforms.

Currently the supported platforms that have been tested on i386, x86_64 and
PPC hardware using z80ex include the following:

- win32 Athlon XP 1.8GHz (2200+) 512Mb DRAM and Windows 2000.

- Linux Athlon AMD64 dual core (3800+) 2Gb DRAM and Ubuntu 8.04.1 Hardy,
  10.04 Lucid Lynx using the 32 bit version.

- FreeBSD Athlon AMD64 dual core (3800+) FreeBSD 6.2 using the 32 bit version.

- Mac OS X (Intel) and MacOS (PPC) models G4 and G5.

## Changes for this release
New for this release:
- Added --cpm3 option for use with LibDsk's RCPMFS type.
- Added detection for LibDsk's 'rcpmfs' type.  If detected and a common
  Microbee format is also in use then reverse skewing is employed.  This
  allows a host directory to behave like a disk image.
- Added optional SRAM battery backup emulation for all ROM based and the 56k
  models.  The backups are saved to the new 'sram' directory.  Each model
  emulated has it's own unique backup file.
- Added --sram-backup option to enable/disable battery backup emulation.
- Added --sram-file option to specify an alternative CMOS file to use.
- Added --sram-load option to enable/disable loading CMOS RAM.
- Added --sram-save option to enable/disable saving CMOS RAM.
- Enable OpenGL support for armv7l (in Raspian Feb 2016).
- Added usage information to README for RCPMS and SRAM Battery Backup.

Changes:
- Compiled up against the LibDsk-1.4.2 library. See the LibDsk ChangeLog.
- Added commented out --sram-backup=off option in 'ubee512rc.sample' to
  disable the new battery backup emulation.
- Added 'rcpm-dsxx' and 'rcpm-ss80' macros to 'ubee512rc.sample'
- Major changes in 'ubee512rc.sample' for ROM and 56k model macros to use
  unique SRAM backup file names for each macro.

Fixed:
- Fixed Makefile 'r' permissions for Unices installs.
- Fixed a warning in 'options.c' concerning 'int x'.
- Fixed a minor bug in crtc.c.
- Fixed 'roms.alias.sample' to closely target various ROM based models.

## Overall features
- SRAM Battery backup emulation for ROM based and 56k models.
- Support for OpenGL and SDL video rendering.
- Scripting language for emulator start-up configuration.
- Configuration file(s) allows default settings and customised models to
  be defined.
- Full Premium (Alpha+) model graphics support. 32K PCG, 8K Screen, 8K
  Colour and 8K Attribute RAM.
- Premium (Alpha+) emulation of the hardware inverse and flashing video
  defined in attribute RAM.
- Premium composite monochrome half intensity emulation.
- 256TC Telecomputer and Teleterm models emulation.
- Third party model emulations, including Dreamdisk and CF.
- Early colour circuit emulation.
- 56/64/128/256/512K/1024K/2048K RAM/DRAM emulation.
- ROM based (tape only) models emulation.
- Floppy and Hard disk drive emulation.
- Specific disk emulations for 1024K, 512K, 256K, 128K, and 64K models using
  Premium/Standard graphics, and the 56K RAM model.
- Selectable display aspect ratios 2:1 and 1:1
- Speaker sound emulation.
- PIO with interrupts emulated.
- RS232 Serial communications for TX/RX.
- Parallel printer output to file(s) options.
- Tape in and Tape out from/to wave files.
- TAP file support.
- Microbee joystick and joystick to key mappings.
- Real Time Clock (RTC) emulation.
- Microbee mouse peripheral emulated.
- Fully mapped 6545 and 256TC/Teleterm keyboard, emulates all keys correctly
  and key repeating works at correct speed.
- All 6545 cursor modes supported.
- Screen is resized to suit the current 6545 registers.
- LibDsk and built in disk image formats supported.  read/write capability
  is available for all floppy drives.
- Access to remote floppy disks on your Microbee.
- Speed execution accuracy and regulation is excellent and very fast in
  turbo mode and even faster if specifying the clock frequency to a high
  value.
- Default speed of emulation is 3.375 MHz but the target frequency can also
  be specified as a command line option.
- CRTC for the VBLANK status is much improved, important for key repeat
  speed and many games.
- Optional colour and monochrome monitor types: colour, green, amber, white,
  black and a user mode.
- Full screen mode.
- Emulator 'hacking' options.
- Z80 Debugging tools built in.
- Quickload mechanism for 8-bit systems.
- Tools allowing files to be copied between the host system and CP/M.
- Emulation of BeeThoven, BeeTalker, DAC parallel port peripherals.
- Emulation of the sn76489 sound IC for Premium and 256TC models.

## Configuration file
The emulator is highly configurable,  the configuration file uses the same
options that are possible on the command line.  Customised sections can be
added making invoking the emulator with options much easier.  Command line
parameters can be used in addition if desired and more than one customised
section can be invoked from the same command line.

Other alternative customised configuration files may also be specified if
required.

## Telecomputer (256TC) emulation
The 256TC model is emulated.  The external serial keyboard option is not
supported.  The Real Time Clock (RTC) is emulated.

## Premium emulation
Premium Microbees were released standard with 16K of PCG and 2 or 8K each of
screen, attribute and colour RAM (VDU) but was able to be expanded to 32K
PCG and the full 8K for VDU RAM.

There is emulation option to select 32K PCG RAM for emulation.

Part of the Premium's new graphics was support for monochrome intensity,
hardware flashing of video and inverse video, these have also been emulated.

Colour video is also part of the Premium series and this too is emulated. 
You have a choice of monitor types to view the output on.

The full 8K of VDU RAM was not actually used as some Premium software would
not work correctly with it unless the programmer was fully aware of the
possibility of the extra 2K RAM banks being installed at a later date, some
machines were shipped with the full 8K for the screen, colour and attribute
RAM but configured to only use 2K for each (3 x 6K wasted).

The problem:
When programming the extra graphics capability of the Premium and selecting
one of the extra PCG banks then attempting to write to VDU RAM (i.e screen,
colour, attribute) would work fine for a machine set for 2K VDU RAM but if
the extra VDU RAM was installed and enabled the incorrect VDU bank would be
selected.

It was the responsibility of the programmer to select VDU bank 0 before
attempting any further access, but programmers were not doing this.  Problem
was that unless the programmer had a full 8K VDU RAM machine for development
the bug would not have been noticed.  If the Premiums were released with 8K
as standard from day one this problem would not have eventuated.

There is an option to use the full 8K VDU RAM and it will behave like a real
Premium with the same problems.

So what was the purpose of this extra VDU RAM then?  Not sure, except it
might have been possible to allow fast switching of displayed video frames
by pre-loading the RAM then adjusting the 6545 display address.

## Teleterm emulation
This model is now working in v4.6.0.

Reference:
Online journal - issue 24, June 1986, pages 25-27.
Online journal - issue 27, September 1986, pages 18-20.

## Premium Plus emulation
The Premium Plus kit model yet to be released by Microbee Technology Pty Ltd
(as at 14-May-2012) http://www.microbeetechnology.com.au/ has been emulated
as far as the Z80 hardware part of the design is concerned which mainly
involves supporting the 1024 Kb of RAM on the core board, the Coldfire
co-processor or any API functionality that it may export at a later stage has
not been emulated at this stage.

The method required to support the 1024 Kb of RAM bank selection has been
provided by the designer of the Premium Plus but has not been tested under
emulation.  Further emulation of this model may be made once more details
are known.

## 56K (APC model) emulation
This model does not have the memory write protect (manually operated switch)
feature implemented yet so can not be made to look like a Basic model.

## Standard colour emulation
Colour emulation for standard models prior to the Premium and 256TC/Teleterm
model Microbees have been emulated.  The optional colour board circuitry,
the colour values and methods used is quite different to the later alpha+
colour models.

## Third party emulation
Support for some third party additions and variations have been emulated.
Currently the Dreamdisk, PJB 512K memory upgrade, Compact Flash Coreboard,
and IDE Hard drive have been emulated.

## Sound emulation
Sound emulation works very well on the machines used for testing.  I have
not had a chance to test on Windows Vista.  Your mileage may vary in this
area depending on your host hardware, operating system and drivers.

From version 5.0.0 a new sound driver has been implemented so some of the
following statements may no longer be applicable:

Be aware that running in turbo mode option with sound can cause the sound
buffer to become full quite quickly and sound could become very distorted
and broken up.

The sound quality is also very dependent on the system timer granularity.
See the 'Speed performance' section for more information.

## Z80 PIO emulation
The Z80 PIO is emulated,  it also is able to generate maskable interrupts.
This allows printing (strobe signal) and serial interrupts to occur.  The
Microbee is able to generate interrupts on any port B bit, currently serial
RX, 256TC/Teleterm keys, RTC, and VSYNC interrupts are emulated.

## RS232 Serial emulation
RS232 Serial emulation for RX and TX is implemented.  This should work for
polled or interrupt driven code.  The serial uses the host's RS232 ports.

## Printer emulation
Parallel printer emulation (Z80 PIO port A) under interrupts is implemented. 
The printer output is directed to files.

## Real Time Clock (RTC)
The RTC is emulated,  it uses the host's system date and time as the initial
values on emulator start up.  The MC146818 RTC appears to have been designed
to keep time and date for the years 1901-2099 only.  It correctly adjusts
for the leap year that occurs in 2000.  The system software around for the
Microbee is typically not Y2K compliant.  Usually the '19' is just hard
coded in for the year part and the year '2008' would be displayed as '19:8'
on a Microbee today.  The ':' is the next ASCII character after the '9'. 
The '9' was the last decade for century 19 (i.e 1998). The emulator gets
around this problem by subtracting 100 for the year value to correct the
value displayed for the last two digits.

There is a '--century' option that can be used to change the century value
for some known ROMs.

The Microbee 'time.com' utility can be used to change the date, day of week
and time but this only remains in force for the current emulated session.

Don't rely on any Microbee applications that may make use of the date for
any calculations.

## SRAM emulation
The amount of SRAM supported by ROM based models is set to 32k by default. 
Model variations are achieved using the --sram option that allows setting
the amount of SRAM to any amount up to 32k in 1k blocks.

Microworld Basic will test the amount of SRAM available and set top of
stack, etc. accordingly.  The --sram option is also useful if needing to
test if a program will work with a reduced SRAM size.

The 'ubee512rc.sample' config file comes with many ROM based model
variations in the form of simple macros.

SRAM Battery backup emulation is also enabled by default for ROM based and
the 56k models.  There are various --sram-- options to control the usage and
the 'ubee512rc.sample' config file uses these to create unique SRAM backup
files for model variations.

The SRAM backup emulation may be disabled by using an --sram-backup=off
option in the config file.

## Joystick emulation
The standard Microbee joystick is emulated.  Any joystick that is supported
by SDL and has switch capability should be suitable. A cheap PC USB Game Pad
was used for development and works well.  The joystick buttons have default
configurations but may be configured as required.

Also supported are joystick to key and command mappings that allow games and
other programs to use joystick control, there are 256 sets that may be
configured, the first 26 of these are selectable from the keyboard using hot
keys.

## BeeThoven sound synthesiser emulation
The Microbee BeeThoven sound synthesiser peripheral that connects to the
Microbee's parallel port is emulated.

## BeeTalker speech synthesiser emulation
The Microbee BeeTalker speech synthesiser peripheral that connects to the
Microbee's parallel port is emulated.

## Digital to Analogue Converter (DAC) emulation
An 8 bit DAC is emulated on the parallel port.

## Microbee Mouse emulation
The Microbee mouse interface is emulated.  The Microbee mouse interface
plugs into the Microbee serial port and uses the DTR and CTS lines for
communications.  A standard Microsoft serial mouse connects to the
interface.

## PIO Port B bit 7 links
The link settings that determines the signal to PIO port B bit 7 are
emulated, an option can be specified to select the required signal.

## Speed performance
From version 5.0.0 a new sound driver has been implemented so some of the
following statements may no longer be applicable:

Emulation speed is excellent when targeting 3.375 and 2.0 MHz, the speed is
consistent and smooth on all programs tested.  Each model emulated uses the
standard CPU clock frequency designed for that model when starting the
emulator.

In turbo mode the speed is very fast especially under Windows 2000 (other
windows not tested yet) and a 1.8 GHz Athlon XP (2200+).  The sound is still
played at the normal rate.

The Turbo mode is great if you do not need Z80 CPU and sound to stay in sync
or need time delays to be accurate.  Great for editing and testing, etc.

Even faster speed is possible by specifying the CPU clock frequency to be
emulated as a command line option.  On the hardware mentioned above, 200+
MHz and possibly as high as 1GHz of Z80 speed was achieved. The frame rate
is reduced at these speeds so the screen does not refresh as quick but this
is all dependent on your host platform's capability.  Reducing the CPU clock
frequency down improves the frame rate.

Using banked CP/M operating systems may reduce the speed achievable as a
large amount of DRAM bank switching is used to access code in other banks
and is especially noticeable when doing nothing and only checking for keys. 
This is not an issue for a real Microbee but under emulation requires 32K of
RAM to be switched in and out every time the bank changes.  For this reason
non-banked CIAB and 56K CP/M systems do not use as much host CPU time.

The speed accuracy (and the sound quality) depends on the granularity of the
system timer.  You need to have reasonable resolution.  If your resolution
is less than 10mS you may find the sound will break up.  Recent Linux
systems now use a lower resolution of 10mS by default which works well.

## Z80 Operating systems
The following operating systems have been tested and are known to work:

- Microbee 128K Standard/Premium versions
- Microbee 128K Hard disk
- Microbee 256TC Telecomputer
- Microbee 56K CP/M
- Microbee CIAB
- PJB v1.2 and 512K v2.0a pre-release
- PJB 512K v2.2P
- PJB 256TC v2.2P
- KRD 512K IDE system (CF)

## Z80 Application software
Too numerous to mention it all, but essentially all system support programs
and 3rd party software work including disk formatting programs.

All machine code games I have tried have worked well.

For Microworld basic programs the list is very long,  there are some very
good graphics and sound affects programs to be had.

Applications for the Premium like 'Simply Write' appear to work well with
out any problems.  I have also tested other Premium graphics programs and
the results has been very good.

For some good samples of Standard and Premium software search through the
MBUG archive located here:

http://www.microbee-mspp.org.au/forum

You will need to join the forum and be an approved member to access the
repository.

Goto the MBUG archive section under Software/Files/MBUG.  Look in the CAT
files for clare1.mwb clareX.mwb, etc, QUIX-2.COM.

Other generic CP/M software can be found here:
http://z80cpu.eu/mirrors/oldcomputers.dyndns.org/cdrom/cpm/simtel/cpmug/
http://www.retroarchive.org/cpm/cdrom/SIMTEL/CPMUG/

# File paths and Variables
## BUILT-IN VARIABLES
uBee512 has internal variable support, variables may be created by the user,
some predefined variables are created at run time that may be accessed using
options.

Any internal variables may be redefined by using first using an --varuset
option followed by a --varset option.  Variables defined by the system takes
precedence.

The internally created variables are:
  UBEE_USERHOME           User's home path on Unices, or the directory
                          containing the ubee512 exe on Windows systems.
  UBEE512 or ubee512      Path to the ubee512 account.
  UBEE_VERSION            Emulator version.
  UBEE_HOST               Host system (UNIX or WIN).
  UBEE_SYS_MAJOR          On Unix systems this will be 'UNIX' On Windows
                          systems it contains one of the following:
                          win9x_me, nt4, nt5 or nt6.  Both systems will use
                          upper case for the variable value.
  UBEE_SYS_MAJOR_VAL      Windows OSVERSIONINFOEX dwMajorVersion member value.
  UBEE_SYS_MINOR          On Unix systems this will be the value of the
                          uname.sysname member.  On Windows systems it contains
                          one of the following: w95, w98, me, nt4_ws,
                          nt4_server, w2000, xp, server_2003, or vista. Both
                          systems will use upper case for the variable value.
  UBEE_SYS_MINOR_VAL      Windows OSVERSIONINFOEX dwMinorVersion member value.
  UBEE_MODEL              Microbee model selected for emulation.
  UBEE_RAM                Amount of main memory (kb) for the emulated model.

  Time and Date           These variables are normally used to form other
                          variables, see TD variable usage in 'ubee512rc'.

  SS                      Seconds. (00-59)
  MM                      Minutes. (00-59)
  HH                      Hours. (00-23) 
  DD                      Month day. (01-2x/3x) 
  mm                      Month. (01-12) 
  YYYY                    4 digit year. (1900-20xx)
  YY                      2 digit year. (00-99)
  ww                      Week day Sun-Sat. (0-6)
  ac                      Week day capitalised. (Sun-Sat)
  al                      Week day lower case. (sun-sat)
  au                      Week day upper case. (SUN-SAT)

The @UBEE512@ variable allows scripts to be portable between systems and
should be used if portability is to be maintained. The configuration files
that come with the uBee512 distribution make use of this.

This variable is set to the uBee512 installed location in Windows or the
account location in Unices, typically it will have the following values:

Windows:
c:\Program Files\ubee512

Unices:
/home/username/.ubee512

This variable may be overridden by specifying an environment variable for it
as that is checked first.

Through out this documentation @UBEE512@ will be used to refer to the
account location.

## ENVIRONMENT VARIABLES
Environment variables may be used by parameters to options.  The variable
may be passed using the shells normal method, i.e. %VAR% in Windows and $VAR
in BASH (Unices), the shell in these cases will simply pass the variable
value through without uBee512 even knowing.  This method is fine for command
line usage but another method that is portable is possible by passing the
variable as @VAR@, this also allows the use of environment variables to be
used in configuration files.

## PATH SLASH CHARACTERS
Forward or back slashes may be used in file paths irrespective of the
program being run under Unices or Windows environments when slash conversion
is enabled. See --slashes option. Unices will see '\' as an escape sequence
when used on the command line and also when found in configuration files and
slash conversion is disabled.

## FILES TO BE OPENED
Existing files will first be searched for in the current directory, if the
path is not found a second search in the default directory will take place.
For the second search the file path specified will be appended to the
default directory path.  The second search is not carried out if a '\',
'.\', or '..\' are the first characters of the path or a ':' character is
used under Windows.

## FILES TO BE CREATED
Files to be created will be placed into the default directory unless a path
to another location is specified by using a '\', '.\', or '..\' as the first
characters of the path or a ':' character is used under Windows.

# Software distributions
Please refer to the INSTALL file located in the doc directory.

# Building from sources
Please refer to the INSTALL file located in the doc directory.

# Installation
Please refer to the INSTALL file located in the doc directory.

## ROM IMAGES
Installing ROMs from version 4.5.0 onwards is now much simpler.  The
'roms.alias' file now supports MD5s and the MD5s are now generated
automatically and placed in a 'roms.md5.auto' file or the user may create a
customised 'roms.md5.user' file which will be used instead. The 'roms.alias'
file explains how to do this.

ROMs may be subject to copyright,  the ROMs you choose and whether you are
entitled to use any copyrighted ROMs can not be answered here.  If you own a
Microbee computer that already has these ROMs you may be entitled to make
images from them or use a convenient image source.

The ROMs required will depend on what model you are trying to emulate. Disk
emulation will require a boot ROM and tape based models will require Basic
ROMs and possibly other support ROMs.

Copy all required ROMs to the following locations:

Windows:
Installed location\ubee512\roms\

Unices:
Your home location/.ubee512/roms/

## Sources
Most of the standard ROMs may be available from this site in the Public
and/or Main repositories:

Public:
http://www.microbee-mspp.org.au/repository

Main:
http://www.microbee-mspp.org.au/forum

## Character ROM
Regardless of what model is being emulated a character ROM image is
required. 'charrom.bin' is the character ROM.  It needs two font sizes for
3.375 MHz models so requires a 3.375 MHz model Microbee 4K ROM image.  If
emulating the 2MHz Microbee model a 2K character ROM could be used.

## DISK IMAGES
Disks may be subject to copyright,  the disk images you choose and whether
you are entitled to use any copyrighted disk software can not be answered
here.  If you already own the original disks you may be entitled to make
images from them or use a convenient image source.

Copy all required disk images to the following locations:

Windows:
Installed location\ubee512\disks\

Unices:
Your home location/.ubee512/disks/

## CP/M OS images
The Peter Broughton 512K CP/M system (ZCPR) can be found here and is in the
public domain:

http://www.microbee-mspp.org.au/forum

Check in the main repository under Software/disks or Software/files

Use a command like:

>ubee512 -a name_of_disk.dsk

## CP/M tools images
Included are some CP/M tools that are designed to only be run under the
uBee512 emulator.  The programs provided allow copying of files between the
host system and CP/M, there are also some other programs, see the TOOLS.TXT
and CHNGELOG.TXT document in the image for more information.  The images
will be placed into the 'disks' directory. For convenience I have provided
images for all the common Microbee formats:

ubee512_cpm_tools.ss80_
ubee512_cpm_tools.ds40_
ubee512_cpm_tools.ds80_
ubee512_cpm_tools.ds82_
ubee512_cpm_tools.ds84_

The underscore '_' character tells uBee512 that these files are not to be
written to, this will NOT apply if using the LibDsk driver to access the
files.  Don't remove this and don't place any other files into these images
as the images are replaced when installing the emulator.

Note the size of these images is smaller than what is expected for a raw
disk image and is normal.

## MODELS
Specific emulation for all Z80 Microbees models is supported, this includes
both floppy disk and tape based machines.

The model to be emulated is specified as an option on the command line with:

--model=type

The models (type) that are emulated are:

256tc  - 256TC Telecomputer, 256K DRAM FDD
p1024k - Premium Plus, 1024K DRAM FDD
1024k -  Standard Premium Plus, 1024K DRAM FDD
p512k  - Premium, 512K DRAM FDD
512k   - Standard, 512K DRAM FDD
p256k  - Premium, 256K DRAM FDD (64K Premium to 256K upgrade)
256k   - Standard, 256K DRAM FDD (64K CIAB to 256K upgrade)
p128k  - Premium, 128K DRAM FDD
128k   - Standard, 128K DRAM FDD (SBC)
p64k   - Premium, 64K DRAM FDD
64k    - Standard, 64K DRAM FDD (CIAB)
56k    - APC 56K RAM, ROM/FDD (Advanced Personal Computer)
tterm  - Teleterm, ROM
ppc85  - Premium, PC85 32K ROM
pc85b  - Standard, PC85 32K ROM using 8/16K Pak ROMs
pc85   - Standard, PC85 32K ROM using 8K Pak ROMs
pc     - PC 32K ROM (Personal Communicator)
ic     - IC 32K ROM
2mhz   - First model and kits, 32K ROM
pcf    - Premium Compact Flash Core board.
scf    - Standard Compact Flash Core board.

The p512k model is emulated if no model option is specified.

## Model defaults
The table below shows the default values for each model.  Command line
options may be used to alter some of the emulation features.  The --model
option must always precede any other overriding options that may be used.

All models boot to address 8000 hex except for the 56K model which uses E000
hex.

TYPE:
This determines the type of model and may be a combination of types.

BOOT:
This is the address at where Z80 code will start to execute from.  There is
no option at present to change this value.

RAM:
This is the amount of DRAM/RAM emulated.  There is no option at present to
change this value.

PCG:
This is the amount of PCG RAM emulated.  The --pcg option can be used to
change the default value for Premium models.

VDU:
This is the amount of VDU RAM emulated.  The VDU RAM includes the screen,
attribute, and colour RAM banks for Premium emulation.  The --vdu option can
be used to change the default value for Premium models only.  By default the
VDU memory is 2K but 8K can be selected.  Setting to 8K can be problematic
and is not advised unless you understand the problems associated with it.

COL:
The colour value indicates the colour version used, 2 is the alpha+
(Premium) colour circuitry, 1 is the standard colour circuitry and no entry
is monochrome.  The standard colour circuit emulation can be enabled with
--col or --col-type and disabled with --mono.  These options only work with
standard models.  A monochrome monitor can be used on any model machine
using the -m or --monochrome option.  Two types of colour monitor may be
emulated for the standard colour models.  See the --col-type option for more
information.

HWF:
This is the hardware flashing/inverse video emulation supported by the
256TC/Teleterm and Premium models.  The 256TC has this as standard.  The
Premium models required some hardware changes to enable this feature to be
used.  The upgraded Premium disk models emulated have this enabled by
default.  The --hwflash option can be used to enable or disable this
emulation.  This setting has no affect on standard models.

MHI:
This is the monochrome half intensity video emulation supported by the
256TC/Teleterm and Premium models.  The 256TC has this as standard.  The
Premium models required some hardware changes to enable this feature to be
used.  The upgraded Premium disk models emulated have this enabled by
default.  The --hint option can be used to enable or disable this emulation. 
The setting has no affect on standard models.

LPEN:
This is the CRTC 6545 Light pen key encoding emulation that every model has
except for the 256TC and Teleterm.  The 256TC/Teleterm models can be forced
to allow this feature by using the --lpen option.

CLK:
This is the CPU clock speed change used by the 256TC and Peter Broughton
system.  When enabled the CPU clock can be switched between 3.375 and 6.750
MHz with software. The --speedsel=n option allows this feature to be enabled
or disabled.

PIOB7:
Link settings on the mother board determines what signal is applied to the
Z80 PIO port B bit 7.  3 of the 4 possibilities are emulated.  The 'net'
option is not emulated.

 piob7=rtc
   use the Real Time Clock (RTC) interrupt output.

 piob7=vsync
   use the Vertical sync signal.

 piob7=pup
   use the pull up resistor.

 piob7=net
   Not implemented.

RTC:
Determines if the Real Time Clock (RTC) emulation is used.  The --rtc=n
option allows this to be enabled or disabled.

PREMG:
Determines if the extra (Premium) graphics are emulated.  There is no option
at present to change this value.

CLOCK:
This is the CPU clock frequency in MHz.  The CPU clock can be altered by
using the -x, --clock=f or --xtal=f options.

## Model     Type     RAM PCG VDU COL HWF MHI LPEN CLK PIOB7 RTC PREMG    CLOCK
256tc  fd          256  16  2   2   Y   Y   -    Y   rtc   Y    Y   3.375/6.750
p1024k fd         1024  32  2   2   Y   Y   Y    -   rtc   Y    Y   3.375
1024k  fd         1024   2  2   2   -   -   Y    -   rtc   Y    -   3.375
p512k  fd          512  32  2   2   Y   Y   Y    Y   rtc   Y    Y   3.375/6.750
512k   fd          512   2  2   -   -   -   Y    Y   rtc   Y    -   3.375/6.750
p256k  fd          256  32  2   2   Y   Y   Y    Y   rtc   Y    Y   3.375/6.750
256k   fd          256   2  2   -   -   -   Y    Y   rtc   Y    -   3.375/6.750
p128k  fd          128  16  2   2   -   -   Y    -   pup   -    Y   3.375
128k   fd          128   2  2   -   -   -   Y    -   pup   -    -   3.375
p64k   fd           64  16  2   2   -   -   Y    -   pup   -    Y   3.375
64k    fd           64   2  2   -   -   -   Y    -   pup   -    -   3.375
56k    fd           56   2  2   -   -   -   Y    -   pup   -    -   3.375
tterm  rom          32  32  2   2   -   -   -    -   rtc   Y    Y   3.375
ppc85  rom          32  16  2   2   -   -   Y    -  vsync  -    Y   3.375
pc85b  rom          32   2  2   -   -   -   Y    -  vsync  -    -   3.375
pc85   rom          32   2  2   -   -   -   Y    -  vsync  -    -   3.375
pc     rom          32   2  2   -   -   -   Y    -  vsync  -    -   3.375
ic     rom          32   2  2   -   -   -   Y    -   pup   -    -   3.375
2mhz   rom          32   2  2   -   -   -   Y    -   pup   -    -   2.000
2mhzdd fd           56   2  2   -   -   -   Y    -   pup   -    -   2.000
dd     fd           56   2  2   -   -   -   Y    -   pup   -    -   3.375
scf   fd/ide/rom   2MB   2  2   -   -   -   Y    Y   rtc   Y    -   3.375/6.750
pcf   fd/ide/rom   2MB  16  2   2   Y   Y   Y    Y   rtc   Y    Y   3.375/6.750

## Known problems
None.

## Non Emulator problems
- Some 'boot.dsk' images may be set to read only and will fail to open in
  the emulator.  Check the file attributes and make sure the file is not set
  as read only.

## Model emulation requirements
The information provided here applies when override options have not been
specified. The override options allow all the ROMs to be configured from the
command line or the configuration file.

Each model uses a particular boot or BASIC ROM(s),  other ROMs are optional,
all the ROMs must be located in the current or ubee512/roms directory.  If
the default model boot ROM image can not be opened the emulator will attempt
to open the fall-back image 'rom1.bin' except for the 56K and 256TC models.

BASIC ROMs for the pc, ic and 2mhz models may be one ROM image or ROM part
images. The emulator will try to use the first ROM file in the list, if this
is not found then ROM parts will be used.

Each FDD model has a default boot disk image name,  the default image must
be located in current or ubee512/disks directory.  If the default model boot
disk image can not be opened the emulator will attempt to open the fall-back
image 'boot.dsk' except for the 56K, 64K models, or the user may specify
what image should be used.

## ROMs aliases
From version 3.1.0 onwards a new optional ROMs alias file (roms.alias) is
used, this allows MD5s or absolute file names to be specified.  The supplied
file has MD5s for all models where ROMs are available and is the recommended
method.  Use of MD5s requires a 'roms.md5.user' or 'roms.md5.auto' file in
the root of the uBee512 directory with the later being auto generated by
ubee512.

See the 'roms.alias' file for more information on how to use ROM aliases.

## disk aliases
From version 3.1.0 onwards a new optional disks alias file (disks.alias) is
used, this allows MD5s or absolute file names to be specified.  The supplied
file does not contain any MD5s.  Use of MD5s requires a 'disks.md5' file
(none supplied) in the root of the uBee512 directory.

The disk aliases also has the added advantage that any uBee512 disk image
type supported may be substituted.  The file extension of the substituted
file determines the image type.  The '.dsk' in the alias name is more for
reference purposes but may be an actual file or link.

See the disks.alias file for more information on how to use disks aliases.

## Default model ROMs and disk images

## Model: 256tc                                  Max  Possible Versions/ROMs
  boot ROM: 256TC.ROM                         16K  v1.15, v1.20
boot image: 256tc.dsk

## Model: p1024k                                 Max  Possible Versions/ROMs
  boot ROM: P1024K.ROM                        16K  bn54, bn56, bn60, ???
extra ROMs: P1024K_2.ROM (optional)           16K  (supported?)
            P1024K_3.ROM (optional)            8K  (supported?)
boot image: p1024.dsk

## Model: 1024k                                  Max  Possible Versions/ROMs
  boot ROM: 1024K.ROM                         16K  bn54, bn56, ???
extra ROMs: 1024K_2.ROM (optional)            16K  (supported?)
            1024K_3.ROM (optional)             8K  (supported?)
boot image: 1024k.dsk

## Model: p512k                                  Max  Possible Versions/ROMs
  boot ROM: P512K.ROM                         16K  bn54, bn56, bn60
extra ROMs: P512K_2.ROM (optional)            16K
            P512K_3.ROM (optional)             8K
boot image: p512k.dsk

## Model: 512k                                   Max  Possible Versions/ROMs
  boot ROM: 512K.ROM                          16K  bn54, bn56
extra ROMs: 512K_2.ROM (optional)             16K
            512K_3.ROM (optional)              8K
boot image: 512k.dsk

## Model: p256k (64K to 256K Upgrade)            Max  Possible Versions/ROMs
  boot ROM: P256K.ROM                         16K  bn54, bn56, bn60
extra ROMs: P256K_2.ROM (optional)            16K
            P256K_3.ROM (optional)             8K
boot image: p256k.dsk

## Model: 256k (64K to 256K Upgrade)             Max  Possible Versions/ROMs
  boot ROM: 256K.ROM                          16K  bn54, bn56
extra ROMs: 256K_2.ROM (optional)             16K
            256K_3.ROM (optional)              8K
boot image: 256k.dsk

## Model: p128k (SBC)                            Max  Possible Versions/ROMs
  boot ROM: P128K.ROM                         16K  bn54, bn56, bn60
extra ROMs: P128K_2.ROM (optional)            16K
            P128K_3.ROM (optional)             8K
boot image: p128k.dsk

## Model: 128k (SBC)                             Max  Possible Versions/ROMs
  boot ROM: 128K.ROM                          16K  bn54, bn56
extra ROMs: 128K_2.ROM (optional)             16K
            128K_3.ROM (optional)              8K
boot image: 128k.dsk

## Model: p64k (CIAB)                            Max  Possible Versions/ROMs
  boot ROM: P64K.ROM                          16K  bn54, bn56
extra ROMs: P64K_2.ROM (optional)             16K
            P64K_3.ROM (optional)              8K
boot image: p64k.dsk

## Model: 64k (CIAB)                             Max  Possible Versions/ROMs
  boot ROM: 64K.ROM                           16K  bn54, bn56
extra ROMs: 64K_2.ROM (optional)              16K
            64K_3.ROM (optional)               8K
boot image: 64k.dsk

## Model: 56k (APC)                              Max  Possible Versions/ROMs
  boot ROM: 56K.ROM                            4K  56KB
boot image: 56k.dsk

## Model: tterm (Teleterm)                       Max  Possible Versions/ROMs
BASIC ROMs: TTERM_A.ROM                       16K
            TTERM_B.ROM                        8K  No ROM, uses 8K SRAM here
  PAK0 ROM: TTERM_C.ROM                       16K
  PAK1 ROM: TTERM_E.ROM                       16K
  PAK2 ROM: TTERM_F.ROM                       16K
  PAK3 ROM: TTERM_G.ROM                       16K
  PAK4 ROM: TTERM_H.ROM                       16K
  PAK5 ROM: TTERM_I.ROM                       16K
   Net ROM: TTERM_NETWORK.ROM                 16K

## Model: ppc85 (Premium PC85)                   Max  Possible Versions/ROMs
BASIC ROMs: PPC85_A.ROM                       16K  ROM-A Basic v5.29e (banked)
            PPC85_B.ROM                        8K  ROM-B Basic v5.29e
  PAK0 ROM: PPC85_PAK0.ROM                    16K  ROM-C v1.3 Wordbee
  PAK1 ROM: PPC85_PAK1.ROM                    16K  ROM-E Command help
  PAK2 ROM: PPC85_PAK2.ROM                    16K  ROM-F BC III PC85 Menu
  PAK3 ROM: PPC85_PAK3.ROM                    16K  ROM-G Graphics/DB
  PAK4 ROM: PPC85_PAK4.ROM                    16K  ROM-H VTEX v2.35
  PAK5 ROM: PPC85_PAK5.ROM                    16K  ROM-I Shell
  PAKx ROM: PPC85_PAK6.ROM - PPC85_PAK7.ROM    8K  External ROMs
   Net ROM: PPC85_NETWORK.ROM                 16K  ROM-D Telcom v3.2.1

## Model: pc85b (Standard PC85 8/16K Pak ROMs)   Max  Possible Versions/ROMs
BASIC ROMs: PC85B_BASIC_A.ROM                  8K  ROM-A Basic v5.25e
            PC85B_BASIC_B.ROM                  8K  ROM-B Basic v5.25e
  PAK0 ROM: PC85B_PAK0.ROM                    16K  ROM-C v1.3 Wordbee
  PAK1 ROM: PC85B_PAK1.ROM                    16K  ROM-E Command help
  PAK2 ROM: PC85B_PAK2.ROM                    16K  ROM-F BC III PC85 Menu
  PAK3 ROM: PC85B_PAK3.ROM                    16K  ROM-G Graphics
  PAK4 ROM: PC85B_PAK4.ROM                    16K  ROM-H Viatel v2.3a
  PAK5 ROM: PC85B_PAK5.ROM                    16K  ROM-I Shell
  PAKx ROM: PC85B_PAK6.ROM - PPC85_PAK7.ROM    8K  External ROMs
   Net ROM: PC85B_NETWORK.ROM                 16K  ROM-D Telcom v3.2.1

## Model: pc85 (Standard PC85 8K Pak ROMs)       Max  Possible Versions/ROMs
BASIC ROMs: PC85_BASIC_A.ROM                   8K  ROM-A Basic v5.25e, v5.24e
            PC85_BASIC_B.ROM                   8K  ROM-B Basic v5.25e, v5.24e
  PAK0 ROM: PC85_PAK0.ROM                      8K  ROM-C v1.3 Wordbee
  PAK1 ROM: PC85_PAK1.ROM                      8k  ROM-E Command help
  PAK2 ROM: PC85_PAK2.ROM                      8K  ROM-F ?
  PAK3 ROM: PC85_PAK3.ROM                      8K  ROM-G ?
  PAK4 ROM: PC85_PAK4.ROM                      8K  ROM-H ?
  PAK5 ROM: PC85_PAK5.ROM                      8K  ROM-I Shell
  PAKx ROM: PC85_PAK6.ROM - PC85_PAK7.ROM      8K  External ROMs
   Net ROM: PC85_NETWORK.ROM (8K)             16K  ROM-D Telcom v3.2.1

## Model: pc85s (Swedish Std PC85 8K Pak ROMs)   Max  Possible Versions/ROMs
BASIC ROMs: PC85S_BASIC_A.ROM                  8K  ROM-A v5.24e
            PC85S_BASIC_B.ROM                  8K  ROM-B v5.24e
  PAK0 ROM: PC85S_PAK0.ROM                     8K  ROM-C v2.0 Wordbee
  PAK1 ROM: PC85S_PAK1.ROM                     8k  ROM-E Database
  PAK2 ROM: PC85S_PAK2.ROM                     8K  ROM-F Kalkyl (Busy-calc III)
  PAK3 ROM: PC85S_PAK3.ROM                     8K  ROM-G Grafik (Graphics)
  PAK4 ROM: PC85S_PAK4.ROM                     8K  ROM-H Videotext
  PAK5 ROM: PC85S_PAK5.ROM                     8K  ROM-I Shell
  PAKx ROM: PC85S_PAK6.ROM - PC85S_PAK7.ROM    8K  External ROMs
   Net ROM: PC85S_NETWORK.ROM (8K)            16K  ROM-D Telcom v3.2.1

## Model: pc                                     Max  Possible Versions/ROMs
BASIC ROMs: PC_BASIC.ROM or                   16K  Basic v5.22e
            PC_BASIC_A.ROM +                   8K
            PC_BASIC_B.ROM                     8K
  PAK0 ROM: PC_PAK0.ROM                        8K  Wordbee v1.2
  PAK1 ROM: PC_PAK1.ROM                        8k  Command help
  PAKx ROM: PC_PAK2.ROM - PC_PAK5.ROM          8K  Internal ROMs
  PAKx ROM: PC_PAK6.ROM - PC_PAK7.ROM          8K  External ROMs
   Net ROM: PC_NETWORK.ROM                     8K  Telcom v3.0, v3.1

## Model: ic                                     Max  Possible Versions/ROMs
BASIC ROMs: IC_BASIC.ROM or                   16K  Basic v5.22e
            IC_BASIC_A.ROM +                   8K
            IC_BASIC_B.ROM                     8K
  PAK0 ROM: IC_PAK0.ROM                        8K  Wordbee v1.2
  PAKx ROM: IC_PAK1.ROM - IC_PAK7.ROM          8K  External ROMs
   Net ROM: IC_NETWORK.ROM                     4K  Telcom v1.0, v1.1, v1.2

## Model: 2mhz                                   Max  Possible Versions/ROMs
BASIC ROMs: 2MHZ_BASIC.ROM or                 16K  Basic v5.10, v5.00
            2MHZ_BASIC_A.ROM +                 4K
            2MHZ_BASIC_B.ROM +                 4K
            2MHZ_BASIC_C.ROM +                 4K
            2MHZ_BASIC_D.ROM                   4K 
  PAK0 ROM: 2MHZ_PAK0.ROM                      8K  edasm
  PAKx ROM: 2MHZ_PAK1.ROM - 2MHZ_PAK7.ROM      8K  External ROMs
   Net ROM: 2MHZ_NETWORK.ROM                   4K  Buzznet

## Model: 2mhzdd (2 MHz Dreamdisk)               Max  Possible Versions/ROMs
  boot ROM: 2MHZDD.ROM                         4K  Dreamdisk v2.18.1
boot image: 2mhzdd.dsk

## Model: dd (3.375 MHz Dreamdisk)               Max  Possible Versions/ROMs
  boot ROM: DD.ROM                             4K  Dreamdisk v2.18.1
boot image: dd.dsk

## Model: pcf (Premium Compact Flash CB)         Max  Possible Versions/ROMs
SYSTEM ROM: PCF.ROM                          256K  Made up of BN56CF and
                                                   Premium PC85 ROMs
boot image: IDE HDD or floppy image

## Model: scf (Standard Compact Flash CB)        Max  Possible Versions/ROMs
SYSTEM ROM: SCF.ROM                          256K  Made up of BN56CF and
                                                   Standard PC85 ROMs
boot image: IDE HDD or floppy image

## Notes
- PC Series III
  The PC series III model was released with Version 3 of Telcom. This was
  the first 8K Network ROM developed from the v1.2 of Telcom.  There does
  not appear to be any Telcom v2.x ROMs.  Version 3 of Telcom included an
  improved machine code monitor, self test and calculator.

  A ROM was introduced providing help for BASIC commands and is termed
  the "COMMAND FILE ROM" located at PAK1.

  Reference: Online Issue 4 - September 1994 Page 36-37

- The PC85S model is essentially a PC85 model with a Swedish ROM set.  The
  ROMs for this are defined in 'roms.alias.sample' and the model specified
  in 'ubee512rc.sample' as [pc85s] and [pc85s-col].

## Microbee Hard disk emulation
The Microbee HDD uses a Western Digital WD1002-5 Winchester/Floppy drive
interface board.  This board is able to control up to 3 hard disk drives and
4 floppy drives.  The emulator supports all WD1002-5 drives.

The HDD was typically 10Mb in size with 2 different models supplied:

Teac model:       (10MB) 306 cylinders, 4 heads, 17 sect/track (use '.HD0')
MiniScribe model: (10MB) 80 cylinders,  4 heads, 63 sect/track (use '.HD1')

uBee512 supports both drive models.  It is not known whether a different HDD
system disk is required for each drive model or whether it can auto detect. 
The examples shown here are aimed at the Teac model.

The following options are used for specifying HDD and floppy images:

--hdd0=file             file path for emulator HDD 0.
--hdd1=file             file path for emulator HDD 1 (Microbee default HDD).
--hdd2=file             file path for emulator HDD 2.

--hdd3=file             file path for emulator WD1002-5 Floppy 1.
--hdd4=file             file path for emulator WD1002-5 Floppy 2.
--hdd5=file             file path for emulator WD1002-5 Floppy 3.
--hdd6=file             file path for emulator WD1002-5 Floppy 4.

The floppy drives look very much like HDDs to the WD1002-5 interface.

The --hddx options may be used when emulating any normal FDC model but will
only be used if the boot ROM and/or operating system have support for the
WD1002-5 board.

The HDD images used must have the same structure as a normal hard disk.  See
'.hd0' and '.hd1' under 'DISK IMAGE FILES' for a predefined HDD image.

The HDD access status is displayed at the the same location where floppy
drive access is seen.  WD1002-5 drives will be numbered from 0-6 and
displayed as '0:', '1:', etc.  Note that this only indicates the actual
WD1002-5 drive being accessed, CP/M will allocate drive letters according to
it's own rules.

To boot from a HDD system with no floppy images specified use:

ubee512 --model=p128k --rom1=HD18.ROM --hdd1=hdd_128k_sys_cpm221.hd0

Alternatively use the 'hdd' macro found in ubee512rc:

## Creating a HDD image
To create a HDD image with a system on it is quite easy using the HDD install
floppy disk.  Enter the following on one line:

ubee512 hdd --hdd1=hd.hd0.temp --hdd3=hdd_128k_sys_cpm221.ds40 --bootkey=f

Make sure the hdd1 image name uses the '.hd0.temp' extension.  This is going
to be our new 10MB HDD image.  You MUST rename this by removing the '.temp'
part after the emulator exits or the contents will be lost the next time it
is used by the emulator.

The --hdd3 image is the HDD install floppy image.

The --bootkey=f option forces HD18.ROM to boot from the floppy disk instead
of the HDD image.

1. Run the INIT program.
2. Select option '2' from the menu to Initialise a Hard Disk.
3. Make sure all options are ticked.
4. Press 'RETURN' to start initialisation.
5. A warning message appears stating the disk has data on it. Answer 'Y'
6. The HDD image will now be created. This takes just over 2 minutes.
7. Enter '0' to exit.

There will now be 4 new CP/M HDD drive partitions B: C: D: E: with each
being about 2.5MB in size.  Drive A: is the floppy.

When the HDD is booted under normal conditions the HDD drives will be A: B:
C: D: with E: being the floppy disk.

Exit the emulator remove the '.temp' part of the the newly created disk
image file name.  If you don't do this it will be erased next time it's
used.

To test the new image:

ubee512 hdd --hdd1=hd.hd0

## Third party WD1002-5/WD2793 dual interface select modification
From version 5.5.0 uBee512 Hard drive emulation allows booting a standard
HD18 HDD boot ROM.  Earlier versions of uBee512 will hang with this ROM as
it can't access the WD1002-5 controller.  By default uBee512 had defaulted
to access the WD2793 and to access the WD1002-5 controller required setting
a 3rd party port at 58h to 1 which then associated ports 40-47h to the
WD1002-5 controller.

The third party boot ROM S60HDD18.ROM which is in circulation is a 16K boot
ROM made up of Microbee's Overdrive model's BN60 and Hard drive HD18 ROMs
and some additional code to select the required 8K section and setting a new
port at 58h.  This hardware design allowed a HDD Microbee the option of
booting from the WD1002-5 or on board WD2793 floppy drive interface.  This
was achieved by the addition of port 58h where writing a 1 to it would
associate ports 40-47h to the WD1002-5 Winchester controller, when port 58h
is 0 then ports 40-47h are associated with the WD2793.

By default the S60HDD18 ROM boots the HD18 part of the ROM where port 58h is
set to 1.  The HD18 ROM section can be made to boot the 1st Winchester
floppy drive by holding down the "F" key on boot or specifying --bootkey=f
under emulation.

To boot the BN60 ROM section requires holding down the "K" key on boot or
specifying --bootkey=k under emulation.

The port at 58h allowed the HDD Microbee to become a dual drive interface
system using either the WD1002-5 controller or the WD2793 FDC and in theory
could be changed as the machine runs which would allow up to 8 physical
floppy drives and 3 hard drives to be accessible.

Under uBee512 5.5.0 both the HD18.ROM and the S60HDD18.ROM may be booted and
both will work but a --port58 option has been added if the dual drive port
at 58h interface is required for the S60HDD18.ROM (gives pre 5.5.0
behaviour).

## IDE Hard disk emulation
Third party emulation of an IDE hard disk drive interface (by workerbee) is
provided.  This is also used by the CF CB project emulation.  The emulation
allows for Primary and Secondary IDEs with Master and Slave selections
resulting in up to four hard drives.

The following options are used for specifying IDE images:

--ide-a0=file           file path for emulator IDE primary master drive.
--ide-a1=file           file path for emulator IDE primary slave drive.
--ide-b0=file           file path for emulator IDE secondary master drive.
--ide-b1=file           file path for emulator IDE secondary slave drive.

The IDE options may also be used with any normal FDC model but will only be
made use of if the boot ROM and operating system have support for it.

The images used must have the same structure as a normal IDE hard disk, this
includes an MBR and partition table.  Information on partitions and their
sizes will be found in the project's documentation.

There is no provision to allow access to real IDE drives as there is no
method in place to return the geometry.  It may also be risky to try
accessing IDE drives at the device level directly anyway.

The disk image types can be any type that is suitable but must be able to
have an adequate size capability and be able to provide the drive geometry. 
See '.hd1' under 'DISK IMAGE FILES' for a predefined HDD image. Other disk
formats that can handle large images will be added in a later release.

The IDE access status is displayed at the the same location where floppy
drive access is seen.  IDE drives will be numbered from 0-3 and displayed as
'0:', '1:', etc.  Note that this only indicates the actual IDE drive being
accessed so CP/M system drives A:, B: etc. using partitions 1 and 2 on
'ide-a0' will always show as '0:'

Depending on the CP/M operating system in use and the configuration of that
system a combination of IDE and floppy drives can make the floppy drives
appear at the first vacant drive letter after all the IDE partitions have
been allocated driver letters.

Example:

--ide-a0=harddisk.hd1 -a floppy1.dsk -b floppy2.dsk

Drive 'ide-a0' may contain 2 CP/M partitions.  These will be allocated CP/M
drives 'A:' for partition 1 and 'B:' for partition 2.  floppy1.dsk will be
allocted 'C:' and floppy2.dsk 'D:'

## SCF and PCF Models
The SCF and PCF models are an emulation of the Compact Flash core board
project.  The same core board (CB) can be used on a Standard or Premium main
board.  The CB also allows the use of IDE drives where up to four CF cards
or a HDD may be used.  Further information can be found in the CF project.

These models use a single 256K ROM, the ROM contains a modified BN56 boot
ROM to allow booting from a IDE hard disk drive and PC85 ROMs. Other ROMs
can be added for Basic, Pak and Net locations.

There are alias names for the ROMs in roms.alias. By default the 256K ROMs
are named SCF.ROM and PCF.ROM.

The xCF emulation boot ROM can boot from an IDE hard disk or floppy disk
depending on what the boot ROM finds.  To boot from an IDE drive an IDE disk
must be specified on the command line.  There is an alias name for this in
disks.alias.

There are CF entries in ubee512rc file that make starting up this model a
simple task:

ubee512 pcf

or

ubee512 scf

To start the xCF emulation with parameters from the command line use
something like this to just use the 8K boot ROM (and no 256K ROM):

ubee512 --model=pcf --rom256k=none --rom1=BN56CF.ROM --ide-a0=cfboot.hd1

or to boot using the 256K ROM image:

ubee512 --model=pcf --rom256k=PCF.ROM --ide-a0=cfboot.hd1

The CF board is able to switch between normal and PC85 mode while running
with some suitable software (if available) but PC85 mode may be forced on
start up using the following option:

--cfmode=pc85

For Unix users there is a 'make-cf-roms.sh' script that may be used to
generate 256K CF ROM images.  This script may be customised to include other
ROMs.

## CONFIGURATION FILE
The emulator is highly configurable, from version 3.0.0 the configuration
file supports a built in scripting language that is able to make decisions
based on the value of variables and so determine how the emulator should be
configured on start up.

The configuration file uses the same options that are possible on the
command line.  Customised sections can be added making invoking the emulator
with options much easier.  Command line parameters may be used in addition
and more than one customised section can be invoked from the same command
line.

A 'ubee512rc' text file (the default) is required to hold the configuration
script. The supplied 'ubee512rc.sample' file can be used as a template.  On
Windows installations this file will be found in the config directory and
on Unices is normally found in:

/usr/local/share/ubee512/config

Alternative configuration files may also be used if the first option on the
command line is --config=my_config.

The default path for configuration files is @UBEE512@

## File structure
- Comment lines are preceded by '#' or ';' and must be the first non-space
  character on the line.  Blank lines are ignored.

- A definition name must be surrounded with square bracket characters '['
  and ']'. All lines below this are part of the definition until a new
  definition name or the end of file is reached.  A maximum of 5000
  definitions are allowed.

- A definition's contents can NOT reference any other definitions.  The
  command line options may include any number of references to definitions
  contained in the file and may be mixed with options.

- Values contained in the [global-start] and [global-end] sections are
  always referenced but their use is optional.  It is not the intention that
  these be used directly by the user.  The [global-start] section is applied
  before any command line options or customised sections are processed.  The
  [global_end] section allows options to override what resulted from a
  command line or a customised section.  i.e. the --model option sets
  default values and the [global-end] section can globally override the
  settings if this is required on a global basis.

- Names used for a definition section must be unique.  If any command line
  option parameters that contains a space before it matches the definition
  name then it will be treated as file definition instead.

- Double quotes '"' may be used around an entry causing it to be treated as
  one option/parameter. On Unices the backslash '\' character can be used to
  allow an escape sequence.  Wild cards will not be expanded.

- Options may be divided up and placed onto new lines to make for easier
  reading.

## Listing the definitions
Use the --lcon or lconw option or use the 'listall' entry found in the
sample file to list all the definition names contained in the configuration
file.  A 'list' entry is also included that will list all entries except for
some early administration entries.

## Examples
A very simple ubee512rc file definition could consist of the following:

# Run a CIAB emulation with standard colour emulation.
[ciab-col]
--fullscreen
--model=64k
--col
-a ciabsyst.ss80

Then to run the 'ciab-col' definition enter:
>ubee512 ciab-col

To disable the full screen mode (toggle it off) enter:
>ubee512 ciab-col -f

This example adds a [com1] definition to the ubee512rc configure file:

# Set up some serial access @ 9600 baud (windows example)
[com1]
--coms=1 --baud=19200 --datab=8

Now we have a [ciab-col] and [com1] definition we could use the following
line that also defines an image for drive B:

>ubee512 ciab-col com1 -b workimage.ss80

The above line could all be defined as one definition but the example shows
how the configuration file and command line options can be combined.

## Scripting language options
There are many options that can be used to test strings with the result
determining the execution path through the script. The language has the
typical 'if', 'else', 'end' structure.  Every '--if-x' test requires a
matching '--if-end' at some point, an '--if-else' does not require it.
Conditionals may be nested up to 1000 levels deep.

All conditional options must be used within a [section].  You can not
conditionally decide to make a section visible.

All the available conditional options are described in 'Conditional
processing' under the 'Command line options' section.

The following are some examples of typical conditional testing,  the
indentation helps to make the script easier to read.  While these examples
don't do anything useful it should show how one can make real use of the
language.

# [example1] This provides a way to enable a script section. To disable this
# section change '--if-true' to '--if-false'.

[example1]
--conio
--if-true
   --echo="The emulator version is: @UBEE_VERSION@"
   --echo="this will always be output"
   --echo="same with this"
--if-end
--exit=-1

# [example2] Some testing based on the host system in use.

[example2]
--if-system=win
  --conio
  --echo="We are on a Windows system."
  --echo="Major type: @UBEE_SYS_MAJOR@  Minor type: @UBEE_SYS_MINOR@"
--if-else
  --if-system=unix
     --echo="We are on a Unix system. The system is: @UBEE_SYS_MINOR@"
  --if-end
--if-end
--exit=-1

# [example3] Show how to set and unset variables and test values an test. 
# To test a variable value it must be enclosed by '@' characters.

[example3]
--conio
--varset="myvar1=Hello World"
--if-eq="@myvar@,Hello World"
   --echo="test 1 resulted in equals"
--if-else
   --echo="test 1 resulted in not equals"
--if-end

--varuset="myvar1"
--varset="myvar1=Hello Worlds"
--if-eq="@myvar@,Hello World"
   --echo="test 2 resulted in equals"
--if-else
   --echo="test 2 resulted in not equals"
--if-end
--exit=-1

# Using the uBee512 Emulator
OSD
---
The OSD provides various confirmation and console dialogues. Built-in
schemes are provided and an existing ones can be modified with options to
provide different colours, size, positioning of the console and the cursor
flash rate.

The dialogue windows are non-blocking, emulation continues in the background
when dialogues are active.

As the OSD dialogues must also operate under SDL video rendering the OSD
uses the current CRTC 6545 display geometry and will automatically adjust
when this changes resolution.

The OSD dialogue windows work in a conventional way but have some
limitations.

## Focus
The OSD is in focus when the Title bar components are highlighted.  To
change focus between the OSD and the emulated program click on the OSD or
somewhere in the application window.

When an OSD dialogue has the focus the ESC key will exit the dialogue
(cancel) and the ENTER key will act on the highlighted button.  The Arrow
and TAB keys can be used to move back and forth on menu buttons.  The button
that has the current selection is surrounded by dashed lines.

## Dragging and resizing
The OSD window may be dragged to any location on the screen by grabbing any
part of the dialogue except for buttons, edges and corners.

The OSD windows may be resized by grabbing any edge or corner. Currently
there is no visual indication when an edge or corner is grabbed.

## Minimising
If the dialogue's minimise button is clicked the window is minimised.  By
default this uses some animation but may be disabled with a '--osd=-all' or
'--osd=-animation' option.  A minimised dialogue will be seen at the bottom
of the display as a short coloured line.  By hovering the mouse cursor close
or on this the window will be restored and have the focus.

Minimising OSD windows uses less host CPU processor time compared to
dragging windows off screen.

## Maximising
A dialogue window can be maximised if a maximise component is included in
the dialogue.

## OSD Options
From version 5.3.0 OSD schemes were introduced.  There are various schemes
built-in that can be selected by using the --osd-scheme option.  The
--osd-list option will list what schemes are available.

Each OSD scheme can be edited to change the colours, size and positioning of
the console and the cursor flashing rate.  The scheme can be changed to
another at any time and will inherit the current size and positioning values
from the existing one in use.

There is an 'osd_scheme.ini.sample' file in the 'config' directory that may
be used for testing, instructions on using it is in the file.

See the OSD options under 'On Screen Display (OSD)' for further information.

## OSD DIALOGUES

## Menu
The main OSD menu can be toggled on and off by pressing the right hand side
mouse button.  From there one of the menu selections may be clicked on.

## About
Displays information and version number for the uBee512 emulator.

## Console
The console is a GUI terminal where uBee512 messages are sent and commands
may be entered.  Most of the options available from the command line may be
entered while the emulator is running.  See the 'UBEE512 CONSOLE' section
for further details.

The inputting of commands currently has no editing capability except for a
destructive backspace and there is no history buffer.

There is currently no provisions for scrolling up and down the window buffer.

The OSD Console may be closed and opened at any stage without losing the
current position.  Any uBee512 output that is sent to the OSD Console while
not active is buffered and will be seen when the dialogue is made active.

The '--help' option when run from the OSD console acts differently compared
to how it does under a stdout device.  When this option is executed it
enters an Interactive help mode and requires pressing the ESC key to exit. 
Interactive help is also exited when the end of the help is reached.  While
in Interactive help the SPACE BAR will advance 8 lines and the ENTER key
advances to the next line.

## Output
This dialogue is used to determine where uBee512 will send it's output to. 
See the '--output' option for more information.

Note: for the 'Console' dialogue to work requires that the OSD is enabled.

## Fullscreen
Toggles between full screen and windowed display.

## Sound
Mutes sound on and off. The GUI status line will display the status of sound
mute.

## Volume +
Increases the sound volume.

## Volume -
Decreases the sound volume.

## Tape (rew)
Rewinds tape input file to start.

## Reset
This is used to reset the emulator.

## Power Cycle
This is used to power cycle the emulator.  The effect is the same as turning
off a Microbee and letting the static RAM completely forget it's contents
before switching back on again.

## Exit
This is used to exit the emulator.

## KEYBOARD
Keyboard emulation of the CRTC6545 'Light pen' keys and the 256TC/Teleterm
internal keyboard is supported, both types can be used at the same time. 
The 256TC/Teleterm key emulation is only possible in the 256TC/Teleterm
models.

All keys are mapped to their respective locations,  this includes the arrow
keys that appeared on the Premium series.  Some keys do not appear on an IBM
keyboard and these have been remapped as follows:

## Keys
256TC/Teleterm Models
SELECT   : PAGEUP

Standard/Premium Models
LINEFEED : PAGEUP
RESET    : PAGEDOWN

SHIFT 0  : SHIFT INSERT

All Models
BREAK    : PAUSE/BREAK

On a Microbee (not 256TC/Teleterm) no key is found above the '0' but there
is a ')' key on a PC keyboard so another method is required to return the
'SHIFT 0' combination as shown above.

## Emulator control
END             : Exit the emulator             
PAGEDOWN        : Reset the emulator
EMUKEY+PAGEDOWN : Power cycle the emulator

A confirmation OSD dialogue should appear when pressing the exit, reset or
power cycle keys if no other dialogues are currently active.  No
confirmation for exit will appear if an '--exit-check=off' option has been
specified earlier.

Pressing the ESC key with the PAGEDOWN key (ESC+RESET) will bypass prompting
the user for any confirmation.

## Emulator commands (hot keys, and joystick commands)
The EMUKEY is the HOME or ALT keys.  The ALT key is not usable in the
256TC/Teleterm models unless the --lpen option is also specified.

The EMUKEY hot keys will repeat if held down.  The repeat rate may be
configured using --cmd-repeat1 and --cmd-repeat2 options.

## Emulator command                 EMUKEY + KEY             Joystick commands
Full screen toggle               EMUKEY + ENTER           C_FSTOG
Tape rewind                      EMUKEY + T               C_TAPER
Disassemble next line            EMUKEY + L               C_DASML
Dump memory (--dump=n)           EMUKEY + D               C_DMP
Dump memory (+  16*lines)        EMUKEY + 1               C_DMPN1
Dump memory (+ 0x1000)           EMUKEY + 2               C_DMPN2
Dump memory (-  16*lines)        EMUKEY + 3               C_DMPB1
Dump memory (- 0x1000)           EMUKEY + 4               C_DMPB2
Dump memory   (repeat)           EMUKEY + 5               C_DMPREP
Register dump                    EMUKEY + R               C_DMPREG
Debug mode off                   EMUKEY + -               C_DBOFF
Debug mode on                    EMUKEY + =               C_DBON
Debug trace on/off               EMUKEY + \               C_DBTRA
Debug step                       EMUKEY + BS              C_DBST1
Debug step * 10                  EMUKEY + [               C_DBST10
Debug step * 20                  EMUKEY + ]               C_DBST20
Joystick disable                 EMUKEY + J + <0>         n/a
Joystick Microbee enable         EMUKEY + J + <1>         n/a
Joystick keys select/enable      EMUKEY + J + <K>         n/a
Sound mute toggle                EMUKEY + S               C_MUTE
Pause emulator on/off            EMUKEY + P               C_PAUSE
Volume up                        EMUKEY + UP              C_VOLU
Volume down                      EMUKEY + DOWN            C_VOLD
Mouse scroll wheel association   EMUKEY + W               C_MWHEEL
Microbee mouse toggle            EMUKEY + M               n/a
Console mode (stdin/stdout)      EMUKEY + C               n/a
OpenGL Filter toggle             EMUKEY + F               C_GLFILT
OpenGL 10% window width          EMUKEY + KP1             n/a
OpenGL 20% window width          EMUKEY + KP2             n/a
OpenGL 30% window width          EMUKEY + KP3             n/a
OpenGL 40% window width          EMUKEY + KP4             n/a
OpenGL 50% window width          EMUKEY + KP5             n/a
OpenGL 60% window width          EMUKEY + KP6             n/a
OpenGL 70% window width          EMUKEY + KP7             n/a
OpenGL 80% window width          EMUKEY + KP8             n/a
OpenGL 90% window width          EMUKEY + KP9             n/a
OpenGL Microbee CRTC X width     EMUKEY + KP_PERIOD       n/a

## MOUSE
## Host
The mouse buttons provide the following functionality when the mouse is not
assigned for Microbee use:

  LEFT BUTTON: Double click toggles full screen mode.
MIDDLE BUTTON: Assign mouse for Microbee use.
 RIGHT BUTTON: Show/Hide the OSD menu.

The mouse scroll wheel may be associated with various actions, see the
--mouse-wheel option for more information. The default association controls
the sound volume:

WHEEL UP   : Volume up
WHEEL DOWN : Volume down

If associated with the OpenGL display then the display may be resized:

  WHEEL UP: Increase OpenGL window size
WHEEL DOWN: Decrease OpenGL window size

The association may be changed at any time by using the EMUKEY + W hot key.

Window resizing in OpenGL mode may also be accomplished by dragging the
window's sides or corners.  After releasing, the Window will resize to the
width and the depth will be set according to the Monitor and Microbee aspect
ratio settings.

Maximised window toggling in OpenGL mode is supported. Note that on Windows
that full screen mode can only be toggled to when the window is not
currently maximised.

## Microbee Mouse
The mouse buttons provide the following functionality when the mouse is
assigned for Microbee use:

LEFT BUTTON   : Microbee application dependent.
MIDDLE BUTTON : Assign mouse for Host use.
RIGHT BUTTON  : Microbee application dependent.

The OSD can not be controlled using the mouse when assigned to the Microbee.
Also the mouse pointer is locked to the emulator display during this time.
The Middle mouse button provides a quick and easy method for switching
between the two.  The status line will display 'm' when the mouse is
assigned to the Microbee.

When the mouse is assigned to for Microbee use then recognition of the mouse
is dependent on the application in use.  For example: the mouse shell only
detects the mouse on start-up, if the mouse is enabled for Microbee usage
when already in the shell it will need to be exited from and restarted to
detect it.

Other Microbee mouse applications may continuously test for the presence of
a mouse and will be configured appropriately.  One such application is
Electric Paintbrush.

# Parallel port peripherals
From version 4.7.0 it is possible to define what peripheral device is
connected to the emulated parallel port.  The parallel printer port is the
default device but may be changed using the following option:

--parallel-port=device

See 'Parallel port device selection' under 'COMMAND LINE OPTIONS' for a
description of all peripheral devices.

From version 5.0.0 this option may be also used to hot-plug parallel port
devices while the emulator is running.

## Printer emulation
A parallel printer peripheral may be emulated by using the '--parallel-port'
option to select it using the following:

--parallel-port=printer

This is the default value.

## JOYSTICK
From version 4.7.0 the '--parallel-port' option must be used to emulate a
Microbee joystick.  Note that this is not required if the joystick is only
being used to map to the Microbee keyboard keys.

To use the joystick emulation you will need:
--parallel-port=joystick

Version 5.0.0 has seen some major improvements to the way joysticks buttons
are arranged with new default assignments.  An optional SHIFT button has
been added with default values to control the running of uBee512.

## The Game controller layout and default configuration
  
               A (top)                      C (top)
              ##  B (bot)  ##                     D (bot)
                                       /                                        \
           /     E                              K     \
          /      |                              |      \
         /    H-- --F        I      J        N-- --L    \
        /        |                              |        \
       /         G                              M         \
      /                  O    ANALOG    T                  \
     /                   |              |                   \
    /                 R--S--P        W--X--U                 \
  ##  /                     |              |                     \
##    /              /   \        /      \        /   \              \
|             /                                    \             |
+            /        TOP VIEW OF A TYPICAL         \            +
 \ ##          /            GAME CONTROLLER             \          /
     
  
    ## Joystick (PIO A)    Button Number    (Shift function)
    A : Player 1            0x04             (MUTE)
B : SPARE               0x06             (FULLSCREEN)
C : Player 2            0x05             (PAUSE)
D :                     0x07             (SHIFT BUTTON)
E : Up                  0x80/0x90        (VOLUME+)
F : Right               0x81/0x91        (WINDOW+)
G : Down                0x82/0x92        (VOLUME-)
H : Left                0x83/0x93        (WINDOW-)
I : Player 1            0x08
J : Player 2            0x09
K : Fire                0x00
L : Fire                0x01
M : SPARE               0x02
N : SPARE               0x03
O : Up                  0x80/0x90        (VOLUME+)
P : Right               0x81/0x91        (WINDOW+)
Q : Down                0x82/0x92        (VOLUME-)
R : Left                0x83/0x93        (WINDOW-)
S :                     0x0a
T : Fire                0x00
U : Fire                0x01
V : SPARE               0x02
W : SPARE               0x03
X : Fire                0x0b
  
Note: The values of 0x8x and 0x9x are Axis and Hat values after being
converted to buttons numbers.  The values shown are using the default
base values.  Values less than 0x80 are typical button numbers returned
by a game controller.

## Microbee joystick
To use an SDL compatible joystick in the standard configuration simply
requires a --js=n option to be specified, n=0 for the first joystick, n=1
for the next, etc.  By default the joystick will be enabled but may be
enabled/disabled using the emulator's hot keys at any time.  The state of
the Microbee joystick emulation can be seen in the status bar.

Use the following options to change the standard assignments of each
Microbee joystick button:

  --js-ACTION=n[,n..]     Associate joystick ACTION with button(s) 'n'. The
                          values for ACTION and the default values are:
                          up    : 0x80, 0x90.
                          right : 0x81, 0x91.
                          down  : 0x82, 0x92.
                          left  : 0x83, 0x93.
                          fire  : 0x00, 0x01, 0x0b.
                          play1 : 0x04, 0x08.
                          play2 : 0x05, 0x09.
                          spare : 0x02, 0x03, 0x06.

The joystick should be enabled before running any program that uses it and
not after.

## Analogue joysticks
Some joysticks may not have the ability to return X and Y direction movement
of a joystick as up, down, left and right button events, the analogue values
returned by these joysticks can be converted to look like simple buttons
using options.  The joystick may need to be switched to analogue mode for
this to work.

This feature will be enabled by default but does require the joystick to be
calibrated by the host system driver.  This should be carried out before
using the --js-axisl option.  Incorrect operation may result if the joystick
is not calibrated correctly.  The Joystick diagnostics described below can
be used to view the analogue values returned by the joystick.

The default button values returned for the movement direction are the same
as a digital joystick but may be changed if required.

Use the following options for analogue joysticks:

  --js-axis=x             Joystick axis mapping to buttons. x=on to enable,
                          x=off to disable. Default is enabled.
  --js-axisb=n            Joystick axis buttons base number. The axis button
                          offsets are 0=up, 1=right, 2=down and 3=left. The
                          base number n is added to the offsets to generate a
                          button number. n may be any value from 0 to 255.
                          Default value is 0x80 (128).
  --js-axisl=n            Determines the thresh hold level for button
                          detection. n may be any value from 1 to 32767.
                          Default value is 3200.

## Joystick Hat
Joystick hat values may be used to return button values:

  --js-hat=x              Joystick Hat mapping to buttons. x=on to enable,
                          x=off to disable. Default is enabled.
  --js-hatb=n             Joystick Hat buttons base number. The Hat button
                          offsets are 0=up, 1=right, 2=down and 3=left. The
                          base number n is added to the offsets to generate
                          a button number. n may be any value from 0 to 255.
                          Default value is 0x90 (144).

## Joystick SHIFT button
One of the buttons on the joystick may be configured as a SHIFT button.  The
SHIFT button may be used in conjunction with another button to produce a
value that can have events assigned to it.

  --js-shift=n            Joystick button to be used as a SHIFT button. n may
                          0-127 or -1 to disable. When a button is pressed in
                          conjunction with the SHIFT button the button's value
                          becomes the sum of 256 plus the button's normal
                          value. Default value is 0x07 (7).

## Joystick keys
The joystick can also be used in key mapping mode,  for this each key (6545
keys only) that is required is assigned to a joystick button. 128 joystick
buttons per key set can be defined, there are 256 key sets available.  Once
the key sets have been configured the one required can be selected from the
keyboard using the emulator's hot keys.

To see what KEY names are available issue a --js-klist option,  the names
are not case sensitive.

Example:

Defining each button requires two options,  these must be used in the order
shown here, let's create a joystick key set that contains '[' for left, ']'
for right, 'q' for up, and 'a' for down movement.  These options should be
placed into your configuration file and given the entry [joy] (or whatever
you want to call it):

[joy]
--js=0

# set up, right, down and left movement keys
--js-kkb=q,0
--js-kkb=],1
--js-kkb=a,2
--js-kkb=[,3
--js-kset=A

You could then use the above definition like so:
>ubee512 joy -a games_1.dsk

The last --js-kset option determines which key set is selected but may be
changed using the emulator's hot keys at any time:

To select this key set use: EMUKEY + J <A>

The status of joystick key set selection can be seen in the status bar.

See the ubee512rc.sample and games.ini.sample file for some predefined
joystick keys.

## Joystick commands
The joystick can also have joystick buttons mapped to emulator commands, the
same commands as used for EMUKEY hot keys are available.  The method used
for setting the associations is identical to the method of setting the
'Joystick keys' except 'C_TYPE' parameters are specified instead of a key. 
The mappings may contain any combination of commands and keys.

The commands will repeat if the joystick button is held down.  The repeat
rate may be configured using --cmd-repeat1 and --cmd-repeat2 options.

To view the available command names issue a --js-clist option,  the names
are not case sensitive.

A preconfigured default set of joystick commands is shown above under
'The Game controller layout and default configuration'

Example:

[joy]
--js=0

# set FS toggle and Pause commands.  The values here are SHIFTED
# i.e. value = button + 256

--js-kkb=C_FSTOG,262
--js-kkb=C_PAUSE,261
--js-kset=A

See the games.ini.sample file for some predefined joystick keys.

## Joystick diagnostics
If you need to find out what buttons, etc. do on your joystick then run this
diagnostics command line and while viewing the standard console output press
buttons on the joystick:

>ubee512 --js=0 --modio=+joystick --conio

## BeeThoven sound synthesiser emulation
The Microbee BeeThoven sound synthesiser peripheral may be emulated by using
the '--parallel-port' option to select it using the following:

--parallel-port=beethoven

## BeeTalker speech synthesiser emulation
The Microbee BeeTtalker speech synthesiser peripheral may be emulated by
using the '--parallel-port' option to select it using the following:

--parallel-port=beetalker

For the BeeTalker emulation to work a SP0256 ROM image is required.

ROMs can be downloaded from: http://spatula-city.org/~im14u2c/sp0256-al2/
The only file required is 'al2.bin'.  There is no need to rename it (any
name will work), just place the file into the roms directory and it will get
found when uBee512 is run.

This ROM's MD5 is specified in the 'roms.alias.sample' file as the alias
'sp0256_1.bin'.  You will need a copy of that entry placed into your working
'roms.alias' file.

## Digital to Analogue Converter (DAC) emulation
An 8 bit DAC peripheral may be emulated by using the '--parallel-port'
option to select it using the following:

--parallel-port=dac

## BeeTalker speech synthesiser emulation
The Microbee BeeTtalker speech synthesiser peripheral may be emulated by
using the '--parallel-port' option to select it using the following:

--parallel-port=beetalker

For the BeeTalker emulation to work a SP0256 ROM image is required.

ROMs can be downloaded from: http://spatula-city.org/~im14u2c/sp0256-al2/
The only file required is 'al2.bin'.  There is no need to rename it (any
name will work), just place the file into the roms directory and it will get
found when uBee512 is run.

This ROM's MD5 is specified in the 'roms.alias.sample' file as the alias
'sp0256_1.bin'.  You will need a copy of that entry placed into your working
'roms.alias' file.

## EA Compumuse sound synthesiser emulation
This module emulates the EA Compumuse, described in the August, 1983
issue.  This device is based on the TI 76489 sound synthesiser IC.

The EA Compumuse sound synthesiser peripheral may be emulated by using
the '--parallel-port' option to select it using the following:

--parallel-port=compumuse

As the device uses the sn76489 IC the internal registers will be in an
unknown state (but usually a regular pattern) on start up and two background
tones can be heard, the tones heard are based on a typical sn76489 IC and
has been emulated here as the default values for more realistic emulation. 
The device will produce noise until a program initialises the IC or by the
use of following option to initialise the register values:

--compumuse-init

The Compumuse supports 3 different clock rates of 1, 2, and 4 MHz with the
default being 2 and may be set with the following option:

--compumuse-clock=n

## Microbee mouse
Microbee mouse emulation may be started from the command line with
--mouse=on, EMUKEY+M or the middle mouse button will toggle mouse emulation
on and off.

Mouse and standard serial emulation is not possible at the same time but may
be switched between the two.

Mouse emulation requires that the Microbee application or system supports a
mouse driver.  Later releases of the Microbee systems had mouse driver code
built in (XBIOS functions 20 and 21) and the v3.0.1 shell and some of it's
support programs used the mouse XBIOS functions.

Other programs like 'Electric Paintbrush' (EP) may also use the mouse.  EP
appears to have mouse driver code built into the application.  When EP
initialises do not move the mouse or it may fail to detect the mouse.

While the mouse is active a small 'm' will appear on the top status line. The
OSD will not have any cursor controls while the Microbee mouse is active,
but the toggle commands can be used to switch between the two.

## UBEE512 CONSOLE
uBee512 provides two different methods where commands (options) may be
entered during the running of the emulator.  One method uses the OSD Console
and the other uses the sdtin/stdout (EMUKEY+C) on the host system.

Most of the options available from the command line may be entered while the
emulator is running.  If a command is not supported a message will be output
stating so.

The console allows disks, printer, tape files, and serial values etc. to be
changed or closed on the fly without having to exit the emulator.  Other
options that are useful whilst running include the setting the Z80 CPU clock
rate, monitor type, etc.

The OSD Console is non-blocking whereas the Stdout Console does block.  The
Stdout method also allows pasting of commands.

Commands (options) must be entered in the same way as would be used on the
command line.  Options must be pre-fixed by '-' or '--' depending on the
options.

When the Stdout Console mode is made active the user must give the console
window the focus to enter commands.  The Stdout Console provides a prompt as
follows:

ubee512>

Pressing the ENTER key with no input will cause the Stdout Console mode to exit. 
The user should then give the focus back to the uBee512 window.

When using the Windows operating system the Stdout Console window that pops
up will remain after exiting.  Do not shut down the console window as this
will cause the emulator to also exit without warning.  To enter more
commands requires the EMUKEY+C to be pressed again when the uBee512 window
has the focus.

# Optional hardware emulation
Some models used optional hardware depending on requirements.  These options
if supported can be enabled and disabled using the --hardware option as
described below:

## WD2793 IC
The 256TC and Premium BN60.ROM model can be forced to boot into menu mode by
specifying the '--nodisk' option. This reports no disk for initial disk
checks and so the menu should appear, further booting (F1) or resetting
should then detect the disk.

The '--mmode' option forces the return of a series of 'M' keys (6545) when
the emulator is started.  This is used for jumping directly into the ROM's
Monitor mode on FDD models.

Floppy models Net/Boot ROMs can be made to boot into Network mode by
disabling the FDC hardware emulation.  To do this use the following option
on the command line:

--hardware=-wd2793

## sn76489an IC
The sn76489an sound synthesiser IC was an option in hardware for the Premium
and 256TC models.  This IC was never installed in factory and required the
user to add it themselves.  By default this device is not emulated.

The device can be enabled using the following option:

--hardware=+sn76489

Normally the sn76489 IC internal registers will be in an unknown state (but
usually a regular pattern) on start up and two background tones can be
heard, the tones heard are based on a typical sn76489 IC and has been
emulated here as the default values for more realistic emulation.  The
device will produce noise until a program initialises the IC or by the use
of the following argument (in place of the previous argument) to initialise
the register values:

--hardware=+sn76489init

## SOUND
From version 5.0.0 a new sound driver has been implemented so some of the
following statements may no longer be applicable:

The emulation of sound is improving as uBee512 is developed further.  From
version 2.7.0 there has been some major improvements and options to
customise the performance.  A problem of a slow distorted sound that had
affected some Windows machines systems should now be resolved.  On my
testing platforms sound is excellent under Windows 2000 and Ubuntu
Hardy/Lucid.

One of the problems associated with sound emulation is keeping the Z80 CPU
emulation and sound generation speed tracking as close as possible to each
other.  If sound emulation runs to fast the sound can break up, if too slow
the sound lags behind what the CPU is doing and has to catch up.

There are a large number of sound options that can be used to fine tune the
sound performance, the default values work very well (for me) and it is
dependent on what system, hardware, the number of other applications running
at the same time, etc.  Some other processes running may have excessive CPU
time causing problems. Web browsers can be a problem when a page is
updating.

One of the best options to try is --snd-hq.  This option sets high quality
sound.  How well this works will be dependent on the host platform.  This is
not set by default so you need to specify the option, if this works well on
your system then you can add it the ubee512rc file in the global section.

See the 'COMMAND LINE OPTIONS' section for further information on this and
other sound options.

uBee512 prior to version 2.7.0 was actually using excessive CPU time
updating the SDL window when nothing needed to be updated.  The CPU time has
been greatly reduced when no display updating is occurring, keep in mind
that some Microbee programs are continuously writing repeated data to the
display memory so the CPU time will not show much improvement.

## DISPLAY
From version 3.0.0 OpenGL and SDL video rendering modes are both supported.
OpenGL is the preferred method as rendering is faster and alternative aspect
ratios are possible.  The default mode is SDL as the OpenGL mode may need
suitable drivers installed to work correctly.  The OpenGL mode can be
enabled by using an '--video-type=gl' option on the command line or by
setting this mode system by system in the configuration file.

## OpenGL Rendering
OpenGL mode allows just about any aspect ratio to be achieved and full
screen mode is truly 'full screen'.  Windows may be resized in a number of
different ways.

As OpenGL handles the stretching to achieve the correct aspect ratio only
one line of Y axis data needs to be written to the display (SDL uses 2).
This speeds up screen writes especially when the display must be redrawn
completely.

## Hardware and drivers
To use OpenGL the video hardware driver must be able to support OpenGL and
will require suitable drivers to support this.  OpenGL is widely used in
Unix environments.  It is also supported on Windows systems but later
systems like XP and Vista no longer support OpenGL out of the box.  The
opengl32.dll file is supplied by the manufacturer's drivers for these later
systems. If you use OpenGL mode and end up with a white display then you
need to look at obtaining drivers and/or settings that support OpenGL.

On Windows systems there may be OpenGL controls found under the display
adapter's advanced section, if not check for the latest drivers supplied by
your video card manufacturer.  Some integrated or older video hardware do
not support OpenGL in hardware.

http://www.opengl.org/pipeline/article/vol003_9/

## Using OpenGL
All the available OpenGL options are described in detail in 'OpenGL
rendering' under the 'Command line options' section.

When OpenGL is used the window's default size will be 50% of the desktop
width.  The aspect ratio of the window will be determined by the current
desktop resolution and the Microbee's display aspect.

By default the Microbee (wanted) aspect ratio is 4:3 (1.333 to 1).  Monitor
aspect ratios for LCD types may be 5:4 or 4:3 and desktop resolutions should
be able to correctly identify these.  CRT monitors are typically 4:3 aspect
but may be using a non 4:3 resolution aspect.

## Monitor aspect ratio
The --gl-aspect-mon option can be used to change the aspect ratio of the
Monitor display. This option may be required if running a 4:3 CRT monitor
with non 4:3 display resolution.

## Microbee aspect ratio
The --gl-aspect-bee option can be used to change the aspect ratio of the
Microbee display.  This should only be used after achieving the correct
monitor aspect ratio.

## Start up window size
The display window may be set to any reasonable size by using options.  The
--gl-winpct and --gl-winpix options can be used to set the display width by
a percentage of the desktop width or by a set number of pixels.  the default
window size is 50% of the desktop width.

## Filter options
Each display mode has a 'soft' and 'sharp' filter rendering method.
Depending on the resolution currently displayed one may look better than the
other.  Small windows tend to look better using the 'soft' mode.  The
default mode can be changed using the '--gl-filter-x' options provided for
each window mode.  The EMUKEY + F hot key can be used to toggle between the
two types for each window mode.

## Windows resizing
The display window may be resized by stretching the window using the mouse,
the mouse scroll wheel, setting window sizes from 10-90% using hot keys,
setting the window size to the Microbee's current CRTC width value, and
toggling between normal and maximised windows.

See the 'KEYBOARD' and 'MOUSE' sections for more information.

## Windows and Unix differences
On Unix systems the --gl-max option can be used to enter a maximised window
mode on start up.  This option does not currently work correctly on Windows
systems so is disabled for that system, maximised can be selected
afterwards.

Toggling between a full screen and a maximised window in Unix is possible
but not under Windows, under Windows you can only toggle between a normal
window and full screen so un-maximising the window is required before
toggling.

On Unix systems toggling between full screen and windows mode will place the
window in the top left corner of the display, on Windows systems the
original window position is re-instated correctly.

## SDL Rendering
The display supports two display ratios of 2:1 and 1:1,  by default this is
set to 2:1.  The 2:1 display ratio is a much improved ratio than what was
provided in version 1.4.0.

When using an 80x24 display mode the 2:1 ratio is very close to a 4:3
monitor aspect ratio.

In BASIC the 64x16 display is not quite as good but still much better than
the 1:1 ratio.

If the display size is 40 characters wide the 1:1 display ratio is enforced.
This keeps Microbee applications like Videotex to the correct aspect ratio.

If the other 1:1 ratio is preferred then a --aspect=1 option can be
specified on the command line.

## STATUS INFORMATION (TITLE BAR)
The title bar is used to show various information during the running of the
emulator.  The information displayed by default is as follows:

uBee512-n.n.n P512K 3.375MHz 8N1:300 [M:m:P:Ti:To:JS:Jn] [vol nn%] [win nn%] D:

Arguments must be prefixed with either a '+' or '-' character.  A '+' will
add and a '-' removes.

## Argument     Description                                Displayed (default)
+/-mute      Sound muted status                         M
+/-mouse     Microbee mouse emulation status            m
+/-emuver    Emulator name and version                  uBee512-n.n.n
+/-model     Base model emulated                        model
+/-speed     CPU clock speed                            3.375MHz
+/-serial    Serial port set up if enabled              1N8:300
+/-print     Parallel printer enable                    P
+/-tape      Tape input/output state                    Ti:To
+/-joy       Joystick status                            JS:Jn
+/-d         Short drive access                         D:

Other optional status arguments:

## Argument     Description                                Displayed (default)
+/-emu       Emulator name                              uBee512
+/-ver       Emulator version                           n.n.n
+/-drive     Long drive access                          Drive D:
+/-model     Base model emulated                        model
+/-ram       Amount of RAM emulated                     nK
+/-sys       System name                                --sys=name
+/-title     Customised title                           --title=name
+/-vol       Always display volume level                [vol nn%]
+/-win       Always display window size                 [win nn%]

## Non optional displayed values
Paused

 A [PAUSED] will always be displayed when the emulator is issued a pause
 command.  No other values following this will be displayed until the paused
 state is turned off.

Debug

 A [status] will always be displayed when the emulator is in debug mode. If
 the emulator is in the paused state then the display will show [PAUSED]
 instead.  The debug [status] will be one of the following:

 [RUNNING] - Debug mode is running.
 [TRACING] - Debug mode is tracing.
 [STOPPED] - Debug mode is stopped.
 [STEP]    - Debug mode is step quiet or step verbose.

## Persist values
Persist values are displayed until their timers expire. The display of the
value may be optional and may be able to configured to always be displayed.
The timer persist value used may also be configured using the --gui-persist
option.

Drive access
 
 This is displayed only if enabled.  A spinning wagon wheel will be
 displayed next to the drive letter during the persist period when the drive
 is accessed.

Volume level [vol nn%]

 This will always be displayed for any volume adjust command, the volume
 level may also be enabled to display all the time with '+vol'.

Window size [win nn%]

 This will always be displayed for any window size adjust action, the window
 size may also be enabled to display all the time with '+win'.

## Control arguments
+/-all

 Clear or set all current status values, other arguments can then follow to
 set or clear flags as required.

+/-left

 Force left hand justification when using a '+' prefix.  Some window
 managers centre the title, if you want this forced left then this argument
 will attempt to do that.

## Other related options
--gui-persist=n
  
 Set the persist time in milliseconds for values that appear on the status
 line, default is 3000mS.

--spad=n

 Sets the number of spaces to be placed between each entry on the title bar. 
 The actual spacing achieved will be dependent on the title font used.
 Default value is 5 spaces.

--title=name

 Define the customised title name to be used when '+title' is used in the
 --status option.

## Example
--spad=10
--title="My title message"
--status=-all+title+model+speed+print+tape+joy+d

The font and size of the text in the title bar is dependent on the
configuration of the Window manager being used.

## DISK IMAGE FILES (BUILT IN SUPPORT)
The following describes the built in support for disk images.  It is
independent of LibDsk.

The emulator currently supports the following types of built-in disk images:

'.DSK'
CPCEMU Disk image format,  this should work on all standard Microbee disks
including the 3.5" Modular disk format.  Copy protected formats (i.e
Honeysoft) will also work on v3.1.0 and later.

'.IMG' or '.NW'
Raw image files in nanowasp v0.22 format, 40T DS DD
The format of this image is: S0-T0..T39, S1-T0..T39

'.DIP' 
Disk Image Plus format.  This is currently under development and is subject
to change and may not be used in the future.

The following raw disk image formats have been introduced to allow easy
creation of images commonly used by the Microbee.  The names also help to
identify what disk can be used in which drive to suit the Microbee OS.

The sectors are in sequential order starting from 1 (or 1 and 21 for DS80)
The format of the singled sided images is: S0-T0, S0-T1, S0-T2, ... The
format of the double sided images is: S0-T0, S1,T0, S0-T1, S1-T1 ...

'.DS40' or '.D40'
Microbee 40T DS DD raw disk image (SBC)

'.SS80' or '.S80'
Microbee 80T SS DD raw disk image (CIAB)

'.DS80' or '.D80'
Microbee 80T DS DD raw disk image (Modular)

'.DS82' or '.D82'
Microbee 80T DS DD raw disk image (Dreamdisk)

'.DS84' or '.D84'
Microbee 80T DS DD raw disk image (PJB)

'.HD0'
Teac HDD (10MB) 306 cylinders, 4 heads, 17 sect/track.

'.HD1'
MiniScribe HDD (10MB) 80 cylinders, 4 heads, 63 sect/track

All disks are recognised by their file name extension,  and is not case
sensitive. A mixture of any of these disk types are allowed for drives A-D.

A disk image containing an operating system is required for drive A.

The images used are specified using the '-a, -b, -c, -d' command line
options when invoking the emulator.

If no image is specified for drive 'A' then boot.dsk will be booted for non
256TC and 56K models.

You must only specify the image type that the OS knows about for each drive.
If you want to use an image of a different size/format for a particular
drive then you must use that OS's set up program to change the drive set up.

## Dynamic image creation
A disk image may be created by uBee512 dynamically when starting the
emulator.  Currently this works for both 'raw' and 'dsk' type disk images,
'dsk' images can only be created if LibDsk support was compiled in.  The
image created will overwrite any previous image by the same file name.


If LibDsk is not compiled in or it fails to create the disk image the built
in raw disk image will attempt to create the disk instead.  This can happen
if a disk format is not recognised by LibDsk.

To make uBee512 create the image, a '.temp' is appended to the file name
when specifying a file name to be mounted by a specific drive.  The new disk
image will contain E5 hex.

After exiting the emulator the image will be available for use but it should
have the '.temp' part removed if the contents are to be kept or it will be
overwritten if specified again.

The file name will determine the format and type to be created.

Example:
-b myimage.ds40.temp
-b myimage.ds40.dsk.temp

Disk images may also be created with the --disk-create option.  For more
information on the --disk-create option see the 'Disk drives' options
section.

## Write protection
Disk images can be made write protected by adding a trailing underscore
character ('_') to the image name.

## LIBDSK IMAGE AND FLOPPY ACCESS
LibDsk is built into uBee512.  It provides the capability to access many
types of disk images, floppy disks and remote disks.

Native Microbee format programs for DS80 and DS40 disks that place side 0
into the physical side 1 sector headers are also able to be used by making
use of some of LibDsk's functions.

The full documentation for LibDsk can be found in the distribution files
here:

http://www.seasip.demon.co.uk/Unix/LibDsk/

The documentation presented here is only intended for use with the emulator.

To access floppy drives on Windows 2000 and above requires a special floppy
driver to be installed. This is available from here:

http://simonowen.com/fdrawcmd/

## LibDsk image types
The following disc image file formats are supported by LibDsk:

dsk
---
Disc image in the DSK format used by CPCEMU.  The format of a .DSK file is
described in the CPCEMU documentation.

## edsk
Disc image in the extended CPCEMU DSK format.

raw
---
Raw disc image - as produced by "dd if=/dev/fd0 of=image". On systems other
than Linux, DOS or Windows, this is also used to access the host system's
floppy drive.

## logical
Raw disc image in logical file system order.  Previous versions of LibDsk
could generate such images (for example, by using the now-deprecated
-logical option to dsktrans) but couldn't then write them back or use them
in emulators.

## floppy
Host system's floppy drive (under Linux, DOS or Windows).

## int25
Hard drive partition under DOS. Also used for the floppy drive on Apricot
PCs.

## ntwdm
Enhanced floppy support under Windows 2000 and XP, using an additional
kernel-mode driver.

## myz80
MYZ80 hard drive image, which is nearly the same as "raw" but has a 256 byte
header.

cfi
---
Compressed floppy image, as produced by FDCOPY.COM under DOS. Its format is
described in cfi.html.

imd
---
Disc images created by Dave Dunfield's ImageDisk utility.

qm
--
Disc images created by Sydex's CopyQM. This is a read-only driver.

## tele
Disc images created by Sydex's TeleDisk.  This is a read-only driver.

## nanowasp
Disc image in the 400k Microbee format used by the v0.22 NanoWasp emulator.

## apridisk
Disc image in the format used by the ApriDisk utility. The format is
described in apridisk.html.

## rcpmfs
Reverse CP/M file system. A directory is made to appear as a CP/M disk. This
is an experimental system and should be approached with caution.

## remote
Remote LibDsk server, most likely at the other end of a serial line.

## Using LibDsk RCPMFS
uBee512 makes it easy to use a host system directory as a disk image.  The
directory specified may also optionally contain a '.libdsk.boot' file which
contains the system tracks.  This allows it to also be booted.

By using RCPMFS it can largely eliminate the use of some other support tools
as CP/M files can be easily copied between a host directory and a disk
image/floppy disk/remote drive or even to another RCPMFS drive!

uBee512 directly supports the standard Microbee disk formats which includes
the following formats:

ds40, ds40s, ss80, ds80, ds82, ds84, ds8b

If no matching disk format is detected then 'rcpmfs' type may still be used
but the user needs to create their own '.libdsk.ini' file in the directory
concerned and only disk formats that have a skew of one will work.

uBee512 uses built in reverse skewing for the above Microbee formats to
allow it to work correctly.  Without that LibDsk would need to modified to
do reverse skewing and would require reverse skew tables at a minimum to
support disks that are skewed.  LibDsk is also not aware of what the CP/M
formats are and the values must be set in a '.libdsk.ini' file.  A better
option would be to have one dedicated definition file that contains all the
required CP/M values as well as skew information that LibDsk could access,
it could use the same format name.

The '.libdsk.ini' file is only auto created if it does not exist or if it
does then only if the 2nd line starts with "AutoCreated=".  The later is a
feature introduced by uBee512 to avoid overwriting a manually created file.

The number of files in the host directory may be any amount but RCPMFS will
only access up to the maximum directory and disk size for the format being
used.  The files need to be in 8.3 CP/M format.  See the LibDsk
documentation for the full rules concerning this.

If a CP/M 3 file system is in use the --cpm3 option should be specified
before each instance of --type=rcpmfs.  This sets Version=3, default is
Version=2 in the '.libdsk.ini' file.

The auto '.libdsk.ini' file created will look similar to this DS40 example:

[RCPMFS]
# This is an auto generated file and will be overwritten each time
AutoCreated=uBee512
BlockSize=2048
DirBlocks=2
TotalBlocks=195
SysTracks=2
Version=2
Format=ds40
secbase=1

The file is not deleted after exiting uBee512 so it may also be used by the
author's patched cpmtools (2.10j or later) if required.

Example 1:
Boot a DS40 56k model as A: and B: 
ubee512 56k --format=ds40 --type=rcpmfs -b path\to\cpm\files

Example 2:
Boot a 'rcpmfs' as A:
ubee512 56k --format=ds40 --type=rcpmfs -a path\to\cpm\files

This example requires the system tracks from a 56k ds40 system image to be
placed into a '.libdsk.boot' file in the 'path\to\cpm\files' directory.  The
uBeeDisk (3.1.0 or later) program may be used to do this and can be
accomplished using the supplied uBeeDisk macros (ubeedisk.ini):

ubeedisk st-ds40 --if=boot_image.dsk --of=path\to\cpm\files\.libdsk.boot

The "--if" file can be any supported type, i.e: RAW, DSK, IMD, etc. 
ubeedisk will figure it out from the '.ext'.

'.libdsk.boot' will contain the system tracks in raw format.

Note:  SETSYS and similar programs (formatters) may not work.  They won't
really be needed anyway.  If you want to change the way a system boots up or
colours etc.  Then do that on a normal disk first then extract the system
tracks from it.

For more information on using 'rcpmfs' type see the LibDsk documentation.

## Using LibDsk to access floppy and disk images
The supplied libdskrc file located in the ubee512 share directory for
Windows and in the user's home path for Unices (.libdskrc) contains formats
specific to the Microbee.  You may add additional formats to this file.  The
LibDsk documentation describes the structure for definitions.

Microbee native format programs placed side 0 into the sector headers on
physical side 1 of double sided disks.  These and other similar disks can be
accessed correctly by using the --side1as0 option.  This option will also
determine what method the internal write track will use. 'ds40' and 'ds80'
formats will automatically use the --side1as0 option.  if the DS40 and DS80
disks used do not have the side 1 issue then disk formats 'ds401' and
'ds801' must be used instead.  Disks created using these last two formats
will also read/write correctly on a Microbee.

The following options are for use with LibDsk (see COMMAND LINE OPTIONS
for more information):

--dstep         Informs LibDsk the next Disk drives option uses double
                stepping to support 48tpi DD disks in a 96tpi DD drive. This
                option must precede each Disk drive option when LibDsk is
                required.

--dstep-hd      Same use as the --dstep option except this is for 48tpi DD
                disks in 96tpi HD drives.

--format=type   Determines the disk format type when using LibDsk.

--lformat       Lists all the LibDsk built in and additional disk formats
                that are available.

--ltype         Lists all the LibDsk driver types that are available.

--side1as0      Informs LibDsk the next Disk drives option uses a disk that
                has physical side one sectors containing 0 in the sector
                headers. (Only used when formatting a disk)

--type=driver   Determines what LibDsk driver will be used for the next Disk
                drives option.

Examples:

Boot from a floppy disk (Native Microbee formatted) that has a system on it:

  Windows 98/Me:
    >ubee512 --type=floppy --format=ds80 -a A:

  Windows 2000/XP/Vista:
    >ubee512 --type=ntwdm --format=ds80 -a A:

  Unices:
    $ ubee512 --type=floppy --format=ds80 -a /dev/fd0

Boot from a disk image and make the emulator's drive B: use the floppy drive:

  Windows 98/Me:
    >ubee512 -a bootimage.ds80 --type=floppy --format=ds80 -b A:

  Windows 2000/XP/Vista:
    >ubee512 -a bootimage.ds80 --type=ntwdm --format=ds80 -b A:

  Unices:
    $ ubee512 -a bootimage.ds80 --type=floppy --format=ds80 -b /dev/fd0

Boot a copy protected disk (or EDSK image):

  Windows 98/Me:
    Does not appear to be possible on this system.

  Windows 2000/XP/Vista:
    >ubee512 --type=ntwdm --format=ss80 -a A:
    >ubee512 --type=edsk --format=ss80 -a bootimage.edsk

  Unices:
    $ ubee512 --type=floppy --format=ss80 -a /dev/fd0
    $ ubee512 --type=edsk --format=ss80 -a bootimage.edsk

Boot from a Teledisk disk image

  Windows W98/Me/2000/XP/Vista:
    >ubee512 --type=tele --format=ds80 -a bootimage.td0

  Unices:
    $ ubee512 --type=tele --format=ds80 -a bootimage.td0

An absolute path must be specified for LibDsk images.  It will not
automatically check the disks directory as is done with the built in image
support.

Access to remote disks on your Microbee:

The 'remote' disk type should allow reading/writing sectors over a serial
port to any floppy disk based Microbee Z80 computer (except dreamdisk
model).

The FDS.COM program, sources and documentation containing some examples can
be found here:

http://www.microbee-mspp.org.au/repository

Check under the 'Utilities' directory.

## Formatting a floppy disk
If you want to use High density 3.5" media then read the section concerning
this below before preceding any further.

The standard Microbee format programs should work from within the emulator.
The format method for double sided disks depends on if the --side1as0 option
or one of the disk formats that selects this automatically is used.  Using
'ds40' or 'ds80' will create formatted disks with the side 1 sector header
issue.  'ds401' and 'ds801' will use the current physical side for the side
value.

Examples:

  Windows 98/Me:
    Not tested

  Windows 2000/XP/Vista:
    >ubee512 -a bootdisk.ds80 --type=ntwdm --format=ds80 -b A:

  Unices:
    $ ubee512 -a bootdisk.ds80 --type=floppy --format=ds80 -b /dev/fd0

The options below can be added to the above command lines to view the output
of the system formatting program:

--conio --modio=+fdc_wtd+fdc_wth

## UNICES FLOPPY ACCESS
This method is largely obsolete if LibDsk is built into the emulator. Please
see the 'LIBDSK IMAGE AND FLOPPY ACCESS' section if LibDsk is available.

10 sector per track (s/t) Microbee floppies that have been formatted with
the native format utilities may not be accessible using the existing device
definitions.  Disks that have the side 1 format issue, unusual sector
numbering, and the other unknowns can make this difficult.  It has been
found that 10 s/t double density disks can be formatted on a Linux or other
Unix hosts that will work in the emulator and the Microbee.

All standard Microbee formats should work except for the DS80 formats as
these have sectors that commence from 21 instead of 1 for the data tracks. 
There may be a method to create a Unix floppy device that will work, though.

To access a floppy disk instead of a 'disk image' we simply specify the
floppy device.  On Linux floppy drive 0 is normally /dev/fd0.  There are
other pre-configured devices that can be used that will match the floppy
media.  In the case of 10 s/t DS82 and DS84 Microbee formats I use:

/dev/fd0u800

You will need to have read/write permission as a normal user for the device.
If there are no suitable preconfigured devices already on your system then
you will need to create one.

## Formatting a compatible floppy
If you want to use High density 3.5" media then read the section concerning
this below before preceding any further.

To format the disk as a user in fd0 place a non-write protected floppy disk
into the drive then enter:

$ fdformat /dev/fd0u800

The formatted disk will contain F6s and not the familiar E5s as used by
CP/M.  To use the disk in CP/M the directory entries will first need to be
filled with E5's

One way to achieve this is to create a disk image using my disk image tools
and call the image 'formatted.ds84'.  The newly created image will contain
all E5s.  Then use 'dd' as follows:

$ dd if=formatted.ds84 of=/dev/fd0u800

ATTENTION !!!: Use extreme care when using 'dd', and DO NOT run as root.
If used incorrectly unrecoverable loss of data could result.

## Creating a compatible floppy disk from a disk image
Creating a compatible floppy from a raw disk image is straight forward under
Linux. A DS84 image can be created with:

$ dd if=myimage.ds84 of=/dev/fd0u800 

This will only work with standard raw disk images.

ATTENTION !!!: Use extreme care when using 'dd', and DO NOT run as root.
If used incorrectly unrecoverable loss of data could result.

## Creating a disk image from a compatible floppy
Creating a disk image from the compatible floppy is straight forward under
Linux. A DS84 image can be created with:

$ dd if=/dev/fd0u800 of=myimage.ds84 bs=512 count=1600

or just:

$ dd if=/dev/fd0u800 of=myimage.ds84

ATTENTION !!!: Use extreme care when using 'dd', and DO NOT run as root.
If used incorrectly unrecoverable loss of data could result.

## Using the floppy disk
To invoke this and boot from a floppy disk I use something like this:

$ ubee512 -a /dev/fd0u800/.ds84

Note that only raw formats are supported.  You can't use '.DSK' formats
directly on floppy disks!

A mix of direct floppy access and disk images can be used if desired.

As the read/write to floppies is being handled by the system, disk caching
will be noticeable on reads.

Don't change floppy disks while the emulator is running.  There is no
support for this at present.  You will have to exit the emulator first
before changing the disk then run the emulator again.

## FLOPPY TO IMAGE SOFTWARE
## Ubeedisk
If you want to convert your Microbee floppy disks to disk images then I have
written a conversion program specifically aimed at converting Microbee disks
on modern PC hardware.  The program can auto detect different Microbee disks
from various Microbee formats and is extremely easy to use.  The program
also allows disks to be formatted and provides some diagnostics ability.

The program provides some data recovery methods along with 'info' files for
each disk image file created. An 'info' file contains information about the
disk image, a status map of all sectors read from the disk and an MD5 stamp
of the associated disk image.

You can find Linux, Windows binaries and sources here:

http://www.microbee-mspp.org.au/repository

Prior to writing that program I used other utilities and I have included
those here as these may still be useful for some formats. My preference is
to use 'ubeedisk' for known Microbee disk types as bad sectors and other
information is also recorded:

## Imagedisk
http://www.classiccmp.org/dunfield/img/index.htm

I used the "ImageDisk 1.17" software successfully on a 386 to generate a
DS40 disk image then converted to a raw disk image format, one of the
programs provided tests the FDC capabilities of the host PC.

Included in this distribution is documentation describing how to use this
package to create Microbee disk images.  See 'microbee_disk_to_image.txt'

## Imagetools
I have created some software tools for manipulating raw and 'DSK' images.
The ubeedisk and LibDsk tools can do most of what these can do but still
have some usefulness.  The distribution can be obtained here:

http://www.microbee-mspp.org.au/repository

Check under the 'Utilities/Imagetools' directory.

## LibDsk tools
LibDsk also has some tools for conversion between floppy disks and images. 
Software sources and Windows binaries are available here:

http://www.seasip.demon.co.uk/Unix/LibDsk/

This section contains some examples of some very useful tools found in
LibDsk.  See the LibDsk documentation for further information on how to use
these.

In all the example commands shown it would be beneficial to add an extra
option of '-retry 5' so that the programs don't exit on a single bad error.

Any command example that ends with the backslash '\' means the rest of the
command is on the next line and may need to be removed.

## dskform
Floppy or image file formatter for emulated machines.

At present it can't replicate the Microbee side 1 issue or format DS80 disks
to have sectors 1-10 on the system tracks.  If the disk is not going to be
used as a system disk this limitation should not present a problem.

Apart from the DS80 problems it should be able to be used for formatting all
the Microbee disks contained in the liddskrc file.

Examples:

Format a floppy disk for the PJB DS84 format

  Windows 98/Me:
    Not tested

  Windows 2000/XP/Vista:
    >dskform -type ntwdm -format ds84 A:

  Unices:
    $ dskform -type floppy -format ds84 /dev/fd0

## dsktrans
Copies from one floppy or image file to another.

Examples:

This will copy a disk image to a floppy disk. The process also formats
the disk at the same time.

  Windows 98/Me:
    Not tested

  Windows 2000/XP/Vista:
    >dsktrans -itype raw -otype ntwdm -format ds84 diskimage.ds84 A:
    >dsktrans -itype dsk -otype ntwdm -format ds84 diskimage.dsk A:
    >dsktrans -itype edsk -otype ntwdm -format ds84 diskimage.edsk A:

  Unices:
    $ dsktrans -itype raw -otype floppy -format ds84 diskimage.ds84 /dev/fd0
    $ dsktrans -itype dsk -otype floppy -format ds84 diskimage.dsk /dev/fd0
    $ dsktrans -itype edsk -otype floppy -format ds84 diskimage.edsk /dev/fd0

This will create a disk image from a floppy disk.

  Windows 98/Me:
    Not tested

  Windows 2000/XP/Vista:
    >dsktrans -retry 10 -itype ntwdm -otype raw -format ds84 A: diskimage.ds84
    >dsktrans -retry 10 -itype ntwdm -otype dsk -format ds84 A: diskimage.dsk
    >dsktrans -retry 10 -itype ntwdm -otype edsk -format ds84 A: diskimage.edsk

  Unices:
    $ dsktrans -retry 10 -itype floppy -otype raw -format ds84 /dev/fd0 diskimage.ds84
    $ dsktrans -retry 10 -itype floppy -otype dsk -format ds84 /dev/fd0 diskimage.dsk
    $ dsktrans -retry 10 -itype floppy -otype edsk -format ds84 /dev/fd0 diskimage.edsk

## dskdump
Sector-level copy from one floppy or image file to another.

This will create an EDSK image from a SS80 floppy disk that contains
different numbers of sectors per track and sector sizes. i.e. A copy protected
disk.

  Windows 98/Me:
    Not tested

  Windows 2000/XP/Vista:
    >dskdump -retry 10 -itype ntwdm -otype edsk -iside 0 -format ss80 A: diskimage.edsk

  Unices:
    $ dskdump -retry 10 -itype floppy -otype edsk -iside 0 -format ss80 /dev/fd0 \
    diskimage.edsk

## Sydex tools
Teledisk by Sydex (Shareware) is widely available on the Internet and can be
used to create TD0 images readable by LibDsk.

Other useful tools by Sydex are Anadisk and CopyQM.

## USING 1.44MB 3.5" HD DISKS AS DD
It is possible to make use of modern 3.5" High Density disks and make these
look like double density instead.

The top left hole (looking from disk front) found on HD disks informs the
drive what media type is being used.  The drive can be tricked into thinking
the disk is a normal double density disk by covering this hole up.  On a
Microbee that has an old double density only drive it makes no difference.

You can find plenty of talk about this subject on the net about whether it
means unreliable data retention, High density media may require larger write
signals and the drives adjust this according to the media inserted. By
covering up the HD hole we are affectively telling the drive to use DD
signals on a HD disk. I would not rely on data being retained for long
periods but I also don't rely on floppy disks full stop.

## TAPE PORT IN/OUT
Tape out to a wave file using the --tapeo option and tape input from a wave
file using the --tapei option have been provided.

A new directory name of 'tapes' will be created in the installation and is
the default location for tape wave files.

The wave file format currently being used is documented further on.  The
format (the default format) may change in the future, compatibility between
different Microbee emulators on the file format will make life easier for
all concerned.  uBee512 currently saves and loads one format type.  The only
flexibility on creating wave files is the ability to set the sample
frequency and volume level desired.  Loading of wave files has more
flexibility in that the data element size, channels, etc. can have values
other than 8 bit data and mono.

The files produced by uBee512 should be very accurate as regards the timing
as this is directly controlled by the Z80 cycle counters.  It will not make
any difference what the speed of emulation is for the accuracy, but the tape
writes and reads are much faster if emulating at high speed rates.  So if
you a bunch of wave files containing programs that you want to load and save
to disk then high speed mode is the way to go.

## Tape sample frequency
The tape output sample frequency can be specified using the --tapesamp
option. Currently the default sample frequency is 22050 Hz but this may
change in the future.

## Tape volume level
The tape output volume level can be specified using the --tapevol option.
The default volume level is 16.

## Loading on a Microbee
The wave files produced by uBee512 can be loaded by a real Microbee with the
red tape plug connected to your PC's speaker on your amplifier/speakers and
the wave file played back.

To do this a mono to stereo adaptor should be used to avoid shorting out the
other audio channel from the PC's amplifier output.  It won't matter what
channel is used for the audio take off.  A replacement load resistor of 100
Ohms is also required.  The unused channel may also require a loading
resistor to keep the PC amplifier stable.

## MICROEBEE          PC AUDIO OUT
 
                   o L (UNUSED)     <--+ (Recommended for unused channel)
##                                        |
              |                        |
              /                        / 
              \ 100 Ohms               \ 100 Ohms
              /                        /
              \                        \
     ##          |                        |
     

## Wave files from cassette
The intention is that DGOS and Kansas City Standard (KCS) format cassette
tapes can be recorded to a wave file (by other software) and then loaded
back into the emulator.  The software used must be able to write the format
being used by uBee512 or converted afterwards.

Conversion tools for Windows:

http://www.beethink.com/AudioConverter.htm
http://www.lightlink.com/tjweber/StripWav/StripWav.html

If using the last one make a copy of your original as it overwrites when
converting.

## Saving data to tape
Data will be written to the wave file whenever the tape out port changes
state. (As tape data is written to in normal usage)

IMPORTANT: The wave file is closed and finalised when exiting the emulator.
You must exit the emulator to use the file you created.  You can then start
the emulator again using the file as an input.

An example of how to use the tape out feature:

A:>basic

First load a '.MWB' file from disk:
>load "myfile"

Save the file to the tape device at 300 baud:
>csave "file1"

Save the file to the tape device at 1200 baud:
>csavef "file2"

Any single wave file can hold as many tape saves as required. A 5 second
quiet period is placed in the wave file between each csave or csavef
command.

## Loading data from tape
To load data from tape requires that an extra step be taken.  After issuing
a cload command in basic you need to select 'Tape (rew)' from the OSD or
press the EMUKEY+T keys.

When there is no more data left to be pulled out of the wave file you will
need to repeat the above tape command to reset the file to the beginning and
allow the data to be accessed.

The tape rewind selection may be used at any time to reset the file to the
beginning, but don't use it during a cload operation unless you're intention
is to deliberately cause a bad load (i.e. abort load).

An example of how to use the tape in feature,  for ROM based models remove
the leading 'c' from the commands:

A:>basic

Load a file from tape:
>cload

Select 'Tape (rew)' from the OSD or press EMUKEY+T

After a few seconds you should see something like:
file1  B *

>cload
file2  B *

You can also specify the file you want to load from the wave file:

Select 'Tape (rew)' from the OSD or press EMUKEY+T to reset the wave stream.

>cload "file2"
file1  B
file2  B *

Consult the BASIC manual for all the tape commands.

## Compressing wave files
As the wave files produced by uBee512 are made up of square waves and not
sinusoidal data the amount of compression that can be achieved is extremely
large, 98% may be typical on a 22 KHz file.

## TAP FILE SUPPORT
TAP file support in uBee512 is an emulator only feature and not an emulation
of the Microbee hardware as the Microbee used software to read and write to
tape employing only minimal circuitry used as a zero crossing detector on the
input to square up the signals.  There is no hardware device that converted
bytes to serial data so there is nothing that can be emulated on that level.

Support for TAP files in uBee512 has been introduced to make it easier to
load programs rather than using the emulated tape port and WAV files.  This
has the advantage that it is fast and the files are small and the format is
retained.  The TAP files also make it easier to understand how the data is
arranged and WAV files can be reproduced from the TAP file as all the
information is stored within it.

The TAP file support is designed for Basic and 56K/64K model Boot ROMs. The
process works by patching known memory locations at run time allowing fast
read/write of tape using normal load/save (cload/csave on disk Basic)
functionality.  This will only work for code that makes use of Basic or E000
functions for reading and writing tape bytes.  Programs such as ROM versions of
Wordbee, EDASM and others should work.  Any copy protected programs that use
a custom loader are unlikely to work.

The patching of code for read and write is based on the whether there is a
corresponding input and output TAP file open and there is Basic in memory
and for Boot ROM patching if it's the correct model.  This allows tape WAV
files to be read (no TAP input open) and saved to a TAP file and vice-versa.

Accessing the TAP functions may also be called from within a program
designed for emulation only by using similar code to that found in
patch_code_input[] and patch_code_output[] of tapfile.c, the patched code
does not have to be installed.

If tape/disk Basic or the 64K model's Boot ROM is being used then the
--tapfilei and --tapfileo options must be used after Basic has been
loaded into memory or in the case of the 64K Boot ROM when the ROM has
relocated itself to 0xe000 in RAM.

See the --tapfile-* options under 'Tape port emulation' for more
information.

Reference: Microbee Disk System Manual (E-4)

8012 and E012  RD_BYTE (DGOS COMPATIBLE)
Assuming that interrupts are already disabled by the calling program,
RD_BYTE reads in a character from the tape interface into A.  All other
registers are preserved.  The tape speed is set by the value of (LO_CYCLES)
at DF5A.  If (LO_CYCLES)=4 then 300 baud is set, if (LOCYCLES)=1 then 1200
baud is set.

8018 and E018  WR_BYTE (DGOS COMPATIBLE)
Assuming interrupts are already disabled, write the byte in A out to the
cassette interface.  All other registers are preserved.  Speed control as
per RD_BYTE.

## RS232 SERIAL COMMUNICATIONS
Serial emulation has been greatly improved from uBee512 version 4.0.0.
RS232 serial communications under interrupts are emulated.  The emulation
makes use of the host PC's RS232 ports so connection to a Microbee computer,
another emulator, terminal, modem or a serial printer should now be
possible.  USB-SERIAL Virtual com port devices have also been tested to
work.

This emulation is for the original Microbee PIO software generated serial
routines.  Baud rates up to 19200 have been tested successfully in both
directions.

The optional Z80 SCC serial IC is not currently emulated.

The options associated with the RS232 serial emulation are:
--coms, --baud, --baudrx, --baudtx, --datab and --stopb 

It is important that a baud rate is specified to match the baud rate you are
using in the Microbee application.  By default this is 300 baud if you don't
tell it otherwise.  If you have problems then check the baud rate settings
and also that you are using the correct com ports.

The defaults are 300 baud, 8 data, 1 stop bit.  To enable the serial
emulation option you must specify the serial communications port to be used
on the host PC.

## Null-modem emulator 
Communication ports can be emulated in Unices and Windows.  For Windows
there is the com0com project:

http://com0com.sourceforge.net/

## Testing
Testing involved connecting two serial ports together on my development
platform with a cross over cable:

## D9 (F)       D9 (F)
RX   2       3 TX
TX   3       2 RX
GND  5       5 GND
RTS  7       8 CTS
CTS  8       7 RTS

7/8 bit data and 1/2 stop bits were tested to work successfully.

Using serial under a Unix style of OS will require that you have access
rights to serial devices.  Typically this involves adding the user in
question to the group associated with the serial device.

The OS disk used for the tests below was a DS40 Premium disk image/floppy
containing Telcom v2.4

Drive B - 'testdisk.ds40.temp' will be created dynamically in the
@UBEE_USERHOME@/.ubee512/disks directory by uBee512 on start-up.  See
'Dynamic image creation'

Linux
(Receiver): $ ubee512 -b testdisk.ds40.temp --coms=/dev/ttyS0 --baud=19200
(Sender):   $ ubee512 --coms=/dev/ttyS1 --baud=19200

When sending to a Microbee from a PC:
(Sender):   $ ubee512 --coms=/dev/ttyS1 --baud=19200 --stopb=2

Windows
(Receiver): > ubee512 -b testdisk.ds40.temp --coms=1 --baud=19200
(Sender):   > ubee512 --coms=2 --baud=19200

When sending to a Microbee from a PC:
(Sender):   > ubee512 --coms=2 --baud=19200 --stopb=2

## Telcom on disk models
Telcom versions 2.0, 2.4 and 3.0 have been tested successfully but always
using the same version for sending and receiving. Four different tests were
conducted:

1. uBee512 -> uBee512 on the same machine
2. uBee512 -> uBee512 on different PCs
3. uBee512 -> Premium Microbee
4. Premium Microbee -> uBee512

The following tests were conducted using Telcom version 2.4.

If sending to a Microbee from uBee512 then use the command line option that
specifies --stopb=2 and set the stop bits in Telcom to 2.  The receiver does
not need to set the extra stop bit.

## Terminal test
Set the baud rate to 19200 for TX and RX for both Telcoms:
>baud 19k

Enter Full duplex terminal mode on each Telcom:
>f

What you type on one Telcom should appear on the other.

Press CTRL+ESC to get back to the main menu on each Telcom.

## File transfer
The following file transfer tests were made:

Telcom        : v2.4
Sender        : uBee512 on Athlon XP 1.8GHz (2200+) 512Mb DRAM and Win 2000
Receiver      : uBee512 on AMD64 +3800 dual core 2Gb + Ubuntu 8.04.1 Hardy
Emulation     : 3.375 MHz
Baud rate TX  : 19200
Baud rate RX  : 19200
Data bits     : 8
Stop bits     : 1
Parity        : none
Handshaking   : none
Amount sent   : 356Kb
Time taken    : 00:09:05 (H:M:S)
Files from    : all from 400K disk boot image drive A:
Files to      : 400K DS40 disk image drive B:
File count    : 43
Retries       : none noted
Errors        : 0

Telcom        : v2.4
Sender        : uBee512 on Athlon XP 1.8GHz (2200+) 512Mb DRAM and Win 2000
Receiver      : Microbee Premium
Emulation     : 3.375 MHz
Baud rate TX  : 19200
Baud rate RX  : 19200
Data bits     : 8
Stop bits     : 2 for sender and 1 for receiver
Parity        : none
Handshaking   : none
Amount sent   : 356Kb
Time taken    : 00:10:01 (H:M:S)
Files from    : all from 400K disk boot image drive A:
Files to      : 400K DS40 floppy disk drive B:
File count    : 43
Retries       : none noted
Errors        : 0

Sender side:
Start Telcom (press '6' from the shell)

Set baud rate to 19200:
>19k

Send the files from drive A:
>send *.*

Receiver side:
We want the files to be transferred to drive B: so exit the shell (enter
'ccp') then log on to drive B:

(A freshly formatted floppy was used in the second test)

>b:

Start Telcom:
>telcom

Set baud rate to 19200:
>19k

Receive the files:
>rec

After a short delay you should notice something happening on the top status
line.  It's usually the receiver side that initiates the start of the
transfer so entering send then rec is normally faster to get things started.

## Redirection in MicroWorld BASIC
Connect a communications port to a communications port on the same or
another PC and start the emulator up with 1200 baud communications.

On Linux:
$ ubee512 --coms=/dev/ttyS0 --baud=1200

On Windows:
> ubee512 --coms=1 --baud=1200

Start Basic and redirect the input to come from the serial port (1200 baud)
in addition to the keyboard.  This example used Basic v6.30.  I found v6.23
to be very slow for this example.

>in# 5 on

On the PC with the other communications port run some terminal software at
the same baud rate.  Anything you type in the terminal will be sent to the
emulator's serial port, you can run commands or copy and paste MWB text
files into the terminal.

To turn the redirection off from the serial port enter:
in# 5 off

Output redirection is also possible using "out# 5 on" or "out# 5" if only
the serial port is to be used for output.

I found that using both input and output redirection at the same time did
not work and produced garbled characters. Don't know if this is an emulator
issue or normal.

## Break signal
This is emulated for TX but not tested.  I don't know if any Microbee
software ever used this signal.

## Unknowns
The emulator may work with Bee modems, this may require that different baud
rates are selectable for TX and RX ?, I have no experience with these type
of modems.

## Other Issues
It does not appear that serial cards found on i386 type hardware support
different board rates for the TX and RX direction on the same port, but this
may be available on a full RS232 implementation, so currently you can only
set one baud rate for both directions.  A later release will address this
issue by using 2 separate independent serial ports and a simple adaptor
circuit.

For now you can ignore the --baudtx and --baudrx options and just use the
--baud option to set the baud rate for both directions.

## Still to do
Starnet networking capability.  Need further information on how PIO port B
bit 7 works.

## PARALLEL PRINTER
Printer emulation on port A of the PIO is emulated under interrupts.
Currently the printer output can be directed to file(s) in one or two
formats.  You can use both formats at the same time if desired.

A new directory name of 'printer' will be created in the installation and is
the default location for printer files.

The options associated with the printer emulation are:
--print, --print-close, --printa and --printa-close

Normally the --print would be used,  the --printa option is used to generate
an ASCII decimal file so the actual values can easily be seen.  Both options
can be used together with different file names if required.

## Examples
This example will boot the default disk and send printer output to the
default print directory:

>ubee512 --print=myprint.prn

The examples that follow assume that the default printer is the parallel
device.

## CP/M redirection
Once in CP/M go to the command line.

To send all console output to the printer:
Press ^P

Send some stuff to the console and printer:
dir a:

Type a file:
type textfile.txt p

Turn off printing output:
Press ^P

This output will not go to the printer file:
dir a:

## Basic
Start BASIC and load a MWB file from tape or disk,  set the list device to
use the parallel port then 'llist' to the printer device, this is a simple
method that can be used to convert files to text format:

>outl#1

>load "prog1"
>llist
>load "prog2"
>llist
>load "prog3"
>llist

prog1, prog2, and prog3 will all be concatenated together in the printer
file.

Exit the emulator and look in myprint.prn

The file may then be printed from the host system using the appropriate
software.

## Copy a file to the host system
A binary or text file can be copied to the host system using the CP/M
pip.com command.  In the case of binary files do not copy more than 1 file
at a time unless you want concatenated binaries.

When copying a binary file, the '[o]' is essential otherwise the first ^Z
byte encountered will terminate the copy:

>pip lpt:=filename.com[o]

Copy a text file that has the typical ^Z character as end of file marker:

>pip lpt:=filename.txt

## VSYNC
The VSYNC signal can be used to feed PIO port B bit 7,  this can be selected
by using the --piob7=vsync option, The PIO emulation allows for interrupts
for this signal.

## Example
This was used as a primitive method to keep time on tape based models.  This
can be demonstrated using the ROM based Telcom.  This example used Basic
5.22e and Telcom v1.2.

>ubee512 --model=ic --piob7=vsync

In Basic start Telcom:
>net

Set the alarm time:
>alarm 0001

Turn the clock on:
>clock on

Now wait for the time to reach 0001 to hear the alarm.  The alarm will stop
after 1 minute.

Exit Telcom to get back to Basic by pressing the ENTER key.

Type in:
>1 LIST
>2 GOTO 1

>run

This should show the clock still being updated in the top right of the
screen and the alarm sounding if active.

Press the BREAK or ^C keys to exit the Basic program loop.

## DEBUGGING TOOLS
The emulator has built in debugging tools, these consist of command line
options and EMUKEYs. These have been introduced to aid in the development of
the emulator but should also prove to be valuable for application debugging
too.

From version 5.5.0 when debug mode is active it is possible to enter debug
options from the console (EMUKEY+C) and for z80 emulation to continue in the
background.

See the 'debugging tools' section under 'COMMAND LINE OPTIONS' for all the
available debugging options.

From version 4.6.0 a great number of additional debugging options have been
added.  Debugging options and the way they work may be changed in future
releases so the latest documentation should always be refereed to.

Many new options that work on the Z80 memory map and banked memory are now
supported.  These and others include the following:

- Break and continue options.
- Break points for PC, RST, port and memory read/write and operations.
- Disassembly of code in Z80 memory.
- Execute code at a specified address
- Fill memory locations.
- Load memory and banks from a file.
- Move memory (copy).
- Save memory and banks to a file.
- Logging debugging options with time/date stamping to a file.
- Push and pop registers and memory.
- Read/write to Z80 ports.
- Search memory for ASCII and integer values.
- Set memory locations.
- Set register values.
- Show the status of ports for both in and out.

Too view the output of the debugging tools a console will need to be
viewable.  In Windows the --conio option must be used or the output will be
sent to stdout.txt instead.

All debugging options and EMUKEY output can be logged to a special file
using time and date stamping.  When this is enabled only option output that
belongs to the debugging group will be logged.  See the '--debug-open' and
'--debug-close' options.

## Z80 code debugging
Debugging mode can be started from the command line or started and stopped
during the running of the emulator.

Z80 Instructions can be single stepped with EMUKEY+BS, stepped 10 or 20
instructions at a time with EMUKEY+[ and EMUKEY+] or continuous trace mode
using EMUKEY+\ to turn on and off.  The Debugging mode can be switched off
with EMUKEY+- and switched on with EMUKEY+=.  The stepping and trace
commands will automatically switch on debugging mode.

During debugging break points will be checked and tracing and code execution
will be halted.  The user can then use the step or trace keys from that
point.

What is displayed in step and trace mode is determined by command line
options.  By default the disassembly fits in an 80 column wide display. 
Only the PC, Z80 Flags and registers AF, BC, DE, and HL are seen.  Other
registers and stack pointer contents can be viewed by using the appropriate
--debug options.  The instruction counter can also be made viewable.

Note: The emulation of the EI instruction appears to execute the instruction
following it so the disassembly of the following instruction is never seen. 
The register values shown next to the EI disassembly is the result of the
instruction that followed it.

## Break points
Break points will be monitored only when debug mode is enabled. Break points
are specified on the command line.  There are various types including PC
address, Port address, RST, memory access address and counter.

Example:
--bp=0x8000 --bp=0x100 --bpr=0x1000

From version 4.6.0 there are also break point options port read/write and
RST instructions that work in a similar way to the existing break point
options.

## Module IO debugging
The result of I/O operations can be viewed and logged using the --modio
option.  This option can take parameters that determines which modules or
parts within a module should be reported.  It can also perform some other
tasks.

Examples:
--modio=+paknet+pioa+piob+piocont

--modio=+log+paknet+pioa+piob+piocont

The last example also sends the output to a log file.  WARNING: Logging can
produce extremely large files in a short period of time, be careful when
using it.

## Peripheral register debugging
The register contents of peripheral devices (including the Z80) can be view
by pressing the EMUKEY+R keys.  What is displayed is determined by the
--regs option.

Example:
--regs=+crtc+rtc+z80

## Memory dump debugging
The Z80 memory map contents can be dumped by pressing one of the EMUKEY+DUMP
keys. The dump keys supported are:

--dump=n              EMUKEY + D
+ 0x0080 (16 * lines) EMUKEY + 1
+ 0x1000              EMUKEY + 2
- 0x0080 (16 * lines) EMUKEY + 3
- 0x1000              EMUKEY + 4
repeat                EMUKEY + 5

Additionally there are --db-dump and --db-dumpl options.

The initial address is set to 0 unless a --dump=addr option is specified on
the command line to change the default value.

The added/subtracted value for EMUKEY+2 and EMUKEY+4 depends on the current
--dump-lines value.  The above shows the values when --dump-lines (lines)
is set to 8 (default).

## Disassembly of code (non executed)
Code in the Z80 memory may be disassembled using --db-dasm and --db-dasml
options.  A EMUKEY+L key may be used to quickly perform a --db-dasml option
from the last address for the current number of lines as set with the
--dump-lines option.

## EMULATION HACKING
The Microbee was very popular with hardware hackers,  so why not have some
emulator hacking capabilities?  The options below can be used to experiment
with the inside workings of uBee512:

-f, --frate=fps
-t, --turbo
-x, --clock, --xtal=f
--vblank=method
--sound=method

A useful combination that prevents multiple keys being produced in quick
succession when running in turbo mode is to use:

-t --vblank=1

This will only work if the keyboard scanning code in the application uses
the VBLANK status of the 6545.  If the key scanning code relies on software
delays then it will not make any difference.

This will also control the speed of any games that rely on the VBLANK
status and play these at the correct rate.

## Speed execution information
An explanation of how uBee512 controls Z80 speed execution is needed here
before progressing any further:

By default a frame rate of 50 FPS and a CPU clock frequency of 3375000 Hz is
used to determine how many cycles of Z80 code are executed in one block:

cycles = clock / framerate

A real Microbee would execute these cycles in this amount of time:

time = cycles / clock

After these cycles have executed some house keeping duties are carried out,
i.e. screen updates, key checks, etc.  The time taken to execute the cycles
and the house keeping duties is measured (timex), so we now know what time
it took and what time it should take (time).  We can now calculate the delay
that is required from these two values:

delay = time - timex

This delay is used to make the emulator run at the stated clock rate.  Turbo
mode simply disables inserting this delay, this then results in the emulator
running as fast as possible.

As the speed is made higher a state will eventually be reached where timex
will be larger than time.  The delay value will go negative and will not be
used.  This state is where the emulator can no longer regulate the execution
speed and will result in the frame rate reducing, essentially it will behave
as if in turbo mode.

Much faster execution is possible by increasing the cycles value and running
in turbo mode.  you can do this by specifying the frame rate with the
--frate option.  By making the frame rate smaller you end up with a higher
cycle value.  The higher cycle value results in the emulator spending more
time executing Z80 code and less time doing house keeping duties.  If the
cycle value is too high it will result in slow updating of the display.

Now that the execution speed is understood the options can be used to play
with the speed.

## Some speed options
A value of 200 MHz causes the screen to update quite slowly so may at first
appear to be slow but it is actually executing code very quickly:

--clock=200.0

Another approach if you want speed is to specify a frame rate value and drop
it into turbo mode, whenever turbo mode is used the frame rate no longer holds
true, it simply determines how many Z80 cycles are executed in one frame.

The example shown below will execute 3375000/10 Z80 cycles per frame with no
additional delays thrown in, the --vblank option is just used to stop keys
exploding out under basic or CP/M:

-t --frate=10 --vblank=1

## QUICKLOAD SUPPORT
Quickload mechanism for 8-bit systems.  Quickload allows a program (or data)
to be loaded into memory from a file located on the host system.  This is
useful for loading programs on ROM based models where the only other method
would require the use of the emulated tape input which is slow and requires
large wave files.

Quickload files requires that the correct version of Microworld Basic is in
memory.  Only ROM 5.xx versions that use the same scratch pad and vector
address values between versions are allowed.  Disk models may also be used
if a 5.xx version tape Basic is in use.  

Basic versions supported are 5.10, 5.22, 5.24, 5.25 and 5.29.  Note that
5.29 Basic uses bank switching and could possibly cause problems if
executing a file is attempted under certain conditions.

Quickload files may be a single file by any name. For convenience quickload
files may be placed into a ZIP file and loaded with the appropriate command
option.

## Single file examples
List the information contained in a quickload file:

--ql-list=filename

Load a quickload file, the optional 'x' will cause the code to be executed
once loaded:

--ql-load=filename,x

## ZIP file examples
Specify the ZIP archive to be used:

--qla-arc=filename.zip

List the directory contents of the ZIP archive. The optional '+v' will give
a verbose report:

--qla-dir=*,+v

List the information contained in all quickload files contained inside the
ZIP archive:

--qla-list=*

Load a quickload file from the ZIP archive, the optional 'x' will cause the
code to be executed once loaded:

--qla-load=filename,x

See 'Quickload support' under 'COMMAND LINE OPTIONS' for a description of
all quickload options.

## COMMAND LINE OPTIONS
uBee512 v5.8.0 - Microbee emulator

Usage: ubee512 [options]

 Control related:

  --account=path          Specify an alternative account location. To create
                          other accounts in the home path on Unices or Windows
                          use path=@UBEE_USERHOME@\name.  Accounts may also be
                          created on removable media. Use this option whenever
                          an alternative account should be used,  the default
                          account is @UBEE_USERHOME@/.ubee512 on Unices and
                          the location of the executed ubee512.exe on Windows
                          machines. This option if used must be the first
                          option declared on the command line.

  --alias-disk=x          Enables/disables checking for disk aliases in the
                          disks.alias file. x=on to enable, x=off to disable.
                          Default is enabled.

  --alias-roms=x          Enables/disables checking for ROM aliases in the
                          roms.alias file. x=on to enable, x=off to disable.
                          Default is enabled.

  --args-error=args       Changes an option error detection flag.

                          This option uses prefixed arguments. See the
                          'Prefixed arguments' section near the end of this
                          help for more information.

                          The arguments supported are:
                          unknown (-+) non-recognised argument error.

  --bootkey=key           Forces a light-pen key scan code on start-up. This
                          is needed by some ROMs to enter certain operating
                          modes. The ASCII key value is converted to a scan
                          code. a-z, and A-Z are converted to codes 1-26 and
                          ASCII 0-9 to codes 32-41.

  --cfmode=x              Force emulation mode for CF model. x=pc85 for PC85
                          mode, x=boot for normal boot emulation. Default is
                          boot mode.

  --config=file           Allows an alternative configuration file to be used
                          or if file='none' then no configuration file will be
                          used. This option if used must be the first or
                          second option declared on the command line. The
                          default file used for configuration is 'ubee512rc'
                          and must be located in the ubee512 directory.

  --cmd-repeat1=n         Set the first delay period in milliseconds to be
                          used for repeated emulator commands. Normally these
                          are activated with EMUKEY and joystick buttons
                          mapped to commands. Default value is 500mS.
  --cmd-repeat2=n         Same as --cmd-repeat1 except this value determines
                          the delay period to be used after the first period.
                          Default value is 50mS.

  --cpu-delay=n           Set the delay method used for controlling Z80 CPU
                          emulation speed. The default value is 0.
                          The arguments supported are:

                          0 : delays give up processor time.
                          1 : delays do not give up processor time.
                          2 : if data is in the sound buffer then use method 1
                              otherwise method 0 applies.

  --dclick=n              Set the double click speed for mouse button events.
                          n may be 100-3000 milliseconds, default is 300mS.

  --exit=x                Forces the emulator to exit. This option is intended
                          to be used inside start up scripts when a condition
                          is not met. x is the exit status value.

  --exit-check=x          Enables/disables exit checking. if enabled the user
                          must confirm before exiting the emulator. x=on to
                          enable, x=off to disable. Default is enabled.

  --gui-persist=n         Set the persist time in milliseconds for values that
                          appear on the status line, default is 3000mS.

  --keystd-mod=args       Set a standard keyboard behaviour modifier flag.
                          These flags provide workarounds when emulating the
                          6545 light pen keys.

                          This option uses prefixed arguments. See the
                          'Prefixed arguments' section near the end of this
                          help for more information.

                          The arguments supported are:
                          all        (+-) all selections.
                          ctrl_shift (+-) extended function keys emulation.

  --lockfix-win32=x       Enables/disables CapsLock key semi-fix code for Win32.
                          This option has been provided in case it needs to be
                          disabled. x=on to enable, x=off to disable. Default
                          is enabled.
  --lockfix-x11=x         Enables/disables CapsLock key semi-fix code for x11.
                          This option has been provided in case it needs to be
                          enabled (possibly on some x11 set-ups). x=on to
                          enable, x=off to disable. Default is disabled.

                          Note: The --lockfix-* options will have no affect if
                          SDL-1.2.14 or later is in use and the CapsLock fix is
                          enabled within SDL. The fix is enabled by default but
                          the behaviour may be modified or disabled with an
                          --sdl-putenv=SDL_DISABLE_LOCK_KEYS=0 option.

  --md5-create=x          Forces the creation of the 'roms.md5.auto' file.
                          If enabled the ROMs directory is scanned and
                          MD5s are created for every file found. No directory
                          recursion is used. x=on to enable, x=off to
                          disable. Default is disabled.

  --mmode                 Forces the return of the 'M' key once when the
                          emulator is started. This is used for jumping
                          directly into the ROM's Monitor mode.

  --mouse-wheel=x         Set the action associated with mouse wheel scrolling
                          The default is 'vol', the association can also be
                          changed with the EMUKEY+W hot key.

                          The arguments supported are:
                          none : no association (does nothing).
                           vol : adjust application volume level.
                           win : resize windows display when in OpenGL mode.

  --nodisk                Set no disks flag,  use to start some boot ROMs in
                          menu mode. This flag will be cleared when any key
                          is pressed.

  --options-warn=x        Turn warnings on/off for unsupported options
                          encountered during run mode. If warning is enabled
                          the offending option is not processed but the
                          processing of options continues. If warning is
                          disabled the offending and all remaining options
                          will not be processed. x=on to enable, x=off to
                          disable. Default is enabled.

  --output=args           Set output devices for all text output. Default
                          output is set to 'osd' and 'stdout' on Unices and
                          'osd' on Windows systems.

                          This option uses prefixed arguments. See the
                          'Prefixed arguments' section near the end of this
                          help for more information.

                          The arguments supported are:
                          all    (+-) all selections.
                          osd    (+-) output to the emulator's OSD console.
                          stdout (+-) output to STDOUT or stdout.txt on win32.
                                      default is (-+) on win32 systems.

  --powercyc              Microbee 'Power Cycle'. (no confirmation checking)

  --prefix=path           Specify an alternative installation location to be
                          used when creating an account on a Unix system.
                          Installed files are normally located in /usr/local/
                          but may be prefixed with 'path'.

  --reset                 Reset z80. (no confirmation checking)

  --runsecs=n             Run the emulator for n seconds then exit. A minimum
                          value of 5 seconds is allowed. Any disk write
                          activity will increase the run value until several
                          seconds of disk write inactivity has passed,  this is
                          used to reduce the chances of exiting at a critical
                          moment. Use this option with care. Setting n=0 will
                          disable this feature and is the default.

  --sdl-putenv=var=value  Sets an SDL environment variable. This can be used
                          to change the behaviour of SDL. The variables
                          supported depends on the SDL version and the SDL
                          documentation should be consulted.

  --slashes=x             Conversion of path slashes to host format. x=on to
                          enable, x=off to disable. Default is enabled.

  --spad=n                Sets the number of spaces to be placed between each
                          status entry on the title bar. The actual spacing
                          achieved will be dependent on the title font used.
                          Default value is 2 spaces.

  --status=args           Status configuration for title bar.

                          This option uses prefixed arguments. See the
                          'Prefixed arguments' section near the end of this
                          help for more information.

                          The arguments supported are:
                          all    (-+) all selections.
                          d      (+-) show short drive access.
                          drive  (-+) show long drive access.
                          emu    (-+) show emulator name.
                          emuver (+-) show emulator name and version.
                          joy    (+-) show joystick status.
                          left   (-+) force left hand justification.
                          model  (+-) show base model emulated.
                          mouse  (+-) show Microbee mouse emulated.
                          mute   (+-) show the sound mute state.
                          print  (+-) show parallel printer enable.
                          ram    (-+) show amount of RAM emulated.
                          serial (+-) show serial port set up if enabled.
                          speed  (+-) show CPU clock speed.
                          sys    (-+) show system name.
                          tape   (+-) show tape input/output state.
                          title  (-+) show customised title.
                          ver    (-+) show emulator version.
                          vol    (-+) always show volume level.
                          win    (-+) always show window size.

  --title=name            Define the customised title name to be used when
                          '+title' is used in the --status option.

  --varset=var[=val]      Set a uBee512 built in environment variable.
                          var contains the variable name and val is an optional
                          value to assign to it. i.e. --varset=myvar=myvalue.
  --varuset=var           Un-set (remove) a uBee512 built in environment
                          variable. var is the variable name.

  --verbose=level         Switch on additional emulator reporting. The default
                          setting does not report any messages during start-up
                          unless error(s) occur. The level value is optional
                          and defaults to 1 if omitted.

 Conditional processing:

                          If any of the following conditionals returns a true
                          result then option processing is enabled, a false
                          result turns processing off until a true condition
                          is met.

  --if-egt=str1,str2      If str1 is equal to or greater than str2.
  --if-elt=str1,str2      If str1 is equal to or less than str2.
  --if-eq=str1,str2       If str1 is equal to str2.
  --if-gt=str1,str2       If str1 is greater than str2.
  --if-lt=str1,str2       If str1 is less than str2.
  --if-negt=str1,str2     If str1 is not equal or greater than str2.
  --if-nelt=str1,str2     If str1 is not equal or less than str2.
  --if-neq=str1,str2      If str1 is not equal to str2.
  --if-ngt=str1,str2      If str1 is not greater than str2.
  --if-nlt=str1,str2      If str1 is not less than str2.
  --if-nset=var           If variable var has not been set.
  --if-set=var            If variable var has been set.

  --if-false              If this is used then set false.
  --if-true               If this is used then set true.

  --if-system=x           If the host system is equal to system x. On POSIX
                          systems (Unix) this value is tested against the value
                          returned by the uname function sysname field. Known
                          arguments supported are:

                          bsd         : Unix BSD system.
                          freebsd     : Unix FreeBSD system.
                          linux       : Unix Linux system.
                          unix        : Unix system.
                          win         : Windows system.
                          win9x_me    : Windows 95, 98 or Me system
                          w95         : Windows 95 system.
                          w98         : Windows 98 system.
                          me          : Windows Millennium system.
                          nt4         : Windows NT4 systems.
                          nt4_ws      : Windows NT4 Work station system.
                          nt4_server  : Windows NT4 Server system.
                          nt5         : Windows NT5 systems.
                          w2000       : Windows 2000 system.
                          xp          : Windows XP system.
                          server_2003 : Windows NT5 Server system.
                          nt6         : Windows NT6 systems.
                          vista       : Windows Vista system.
                          w7          : Windows 7 system.
                          w8          : Windows 8 system.
                          w8.1        : Windows 8.1 system.
                          w10         : Windows 10 system.

  --if-else               If last conditional resulted in false.
  --if-end                End of a conditional block.
  --if-cmpmode=x          Set the method used for comparing values, x=0 uses
                          'C' style strverscmp() and x=1 uses strcmp(). Default
                          method is 0.

 Debugging tools:

  --bp=addr[,addr..]      Set a Z80 PC address break point(s). This option can
                          be used to set one or more break points separated by
                          comma characters. The break point is cleared after
                          detection.
  --bpclr=addr            Clear a Z80 address break point. 'a' or 'all' may
                          be specified for 'addr' to clear all break points.'
  --bpr=addr[,addr..]     Same action as --bp option except the break point is
                          not cleared after detection.

  --bpc=count             Set a Z80 break point determined by the number of
                          instructions executed. Can only be specified once.
                          A break point can only be detected when in debug
                          mode.

  --dasm-lines=n          Set the number of lines for disassembly. The default
                          value is 1.

  --db-bp=addr            Alternative option name for --bp.
  --db-bpclr=addr         Alternative option name for --bpclr.
  --db-bpr=addr           Alternative option name for --bpr.
  --db-bpc=count          Alternative option name for --bpc.

  --db-bpos=s,f           Set a break point when the PC is outside of the
                          address range 's' and 'f' (inclusive). This may be
                          cleared using a 'c' or 'clr' for 's'. The break
                          point once triggered must re-enter the address
                          range before another break can occur.

  --db-bp-port=d,p,n      Set a breakpoint for a read/write on port 'p' with
                          a matching value 'n'. 'n=*' may be used to match any
                          value. The port direction 'd', may be 'w' for writes
                          and 'r' for reads.
  --db-bpclr-port=d,p     Clear a breakpoint for port 'p', for port direction
                          'd', where 'd' may be 'w' for writes and 'r' for
                          reads.
  --db-bpr-port=d,p,n     Same action as --db-bp-port option except the break
                          point is not cleared after detection.

  --db-bp-rst=x           Set a Z80 RST n break point. This option can be
                          specified as many times as is required. A break
                          point can only be detected when in debug mode. The
                          break point is cleared after detection. n may be
                          any RST instruction: 00h, 08h, 10h, etc.
  --db-bpclr-rst=n        Clear an RST n break point.
  --db-bpr-rst=n          Same action as --db-bp-rst option except the break
                          point is not cleared after detection.

  --db-bp-mem=d,s[,f]     Sets a memory read/write breakpoint for the memory
                          range 's' to 'f' (inclusive). The direction 'd', may
                          be 'w' for memory writes or 'r' for memory reads.
  --db-bpclr-mem=d,s[,f]  Clears a memory read/write breakpoint for the memory
                          range 's' to 'f' (inclusive). The direction 'd', may
                          be 'w' for memory writes or 'r' for memory reads.
  --db-bp-meml=d,s,l      Sets a memory read/write breakpoint for the memory
                          range 's' for 'l' bytes. The direction 'd', may
                          be 'w' for memory writes or 'r' for memory reads.
  --db-bpclr-meml=d,s,l   Clears a memory read/write breakpoint for the memory
                          range 's' for 'l' bytes. The direction 'd', may
                          be 'w' for memory writes or 'r' for memory reads.

  --db-break, --break     Stop Z80 code execution (enters paused state).

  --db-cont, --cont       Continue Z80 code execution (pause off).

  --db-dasm=s,f           Disassemble Z80 code starting at address 's' and
                          finishing at 'f'. The code is only disassembled and
                          is not executed.
  --db-dasml=[s[,l]]      Disassemble Z80 code starting at address 's' for 'l'
                          number of lines. If the optional parameters are
                          omitted the disassembly continues on from the last
                          address for the current line value as set with the
                          --dasm-lines option. The code is only disassembled
                          and is not executed.

  --db-dump=s,f[,h]       Dump memory starting at address 's' and finishing at
                          'f'. The optional 'h' value determines if a header is
                          used. A '+h' enables and a '-h' disables the header.
                          The default header setting is determined by the
                          --dump-header option if the 'h' value is omitted.
  --db-dumpb=t,b,s,f[,h]  Dump bank memory type 't', bank 'b', starting at
                          offset 's' and finishing at 'f'. The 'h' value is the
                          same as that described for the --db-dump option.
                          See 'Bank t arguments' section near the end of this
                          help for more information.
  --db-dumpl=[s[,l][,h]]  Dump memory starting at address 's' for 'l' number of
                          lines. If the optional parameters are omitted the
                          dump continues on from the last address for the
                          current line value as set with the --dump-lines
                          option. The 'h' value is the same as that described
                          for the --db-dump option.
  --db-dumplb=t,b,s,l[,h] Dump bank memory type 't', bank 'b', starting at
                          offset 's' for number of lines 'l'. The 'h' value is
                          the same as that described for the --db-dump option.
                          See 'Bank t arguments' section near the end of this
                          help for more information.
  --db-dumpp=d,p[,p..]    Dump the current Z80 8 bit port 'p' input/output
                          state values for direction 'd', where 'd=i' for
                          inputs and 'd=o' for outputs. All 256 ports will be
                          dumped if 'a' or 'all' is specified for 'p'. This
                          option will not read or write to the port.
  --db-dumpr              Dump current value of all Z80 registers using 'all'
                          output settings.

  --db-fillb=t,b,v        Fill bank memory type 't', bank 'b' using value 'v'.
                          All banks belonging to type 't' may be filled by
                          specifying 'a' or 'all' for bank 'b'.
                          See 'Bank t arguments' section near the end of this
                          help for more information.
  --db-fillm=s,f,v        Fill memory with a value. Fill memory starting at
                          address 's' and finishing at 'f' with value 'v'. This
                          works on the current Z80 memory map configuration.
                          Memory destinations and locations will be dependent
                          on the current port 0x50 setting on DRAM models,
                          other things like character ROM may also be in the
                          memory map and needs to be taken into account.

  --db-findb=t,s,f,o,d    Search banked memory type 't', starting with bank
                          's', finishing at bank 'f' with an initial starting
                          offset of 'o' in the first bank.  The 'f' value may
                          be 'a' or 'all' for all remaining banks. The
                          'bank:offset' values where matches are found will be
                          displayed. The search criteria is passed in 'd' and
                          is defined in the --findm option.
  --db-findm=s,f,d        Search memory starting at address 's' and finishing
                          at 'f' with the address displayed where a successful
                          search was located. The search criteria is passed in
                          'd' which may consist of any of the following values
                          with each one separated by a ',':

                          a     : Following value is ASCII (next only).
                          b     : Following values are bytes (default).
                          c     : As for 'a' but matches any case for
                                  everything! Avoid searching for integer
                                  values in the same search if using this.
                          w     : Following values are words.
                          byte  : Byte value.
                          word  : Word value.
                          ASCII : ASCII characters.

  --db-go=addr            Start executing code at address 'addr'. Emulation
                          will be switched on if currently in a paused state.

  --db-loadb=t,b,file     Loads bank memory type 't', bank 'b', with data from
                          a file.  All banks that belong to type 't' will be
                          loaded if 'a' or 'all' is specified for 'b'.
                          See 'Bank t arguments' section near the end of this
                          help for more information.
  --db-loadm=a,file       Load memory address 'a' with data from a file. Up to
                          65536 bytes may be loaded, if the value is exceeded
                          the process terminates without error.

  --db-move=s,d,a         Move (copy) memory from source address 's' to
                          destination 'd' for amount 'a'.

  --db-popm               Restore state of memory from an earlier --db-pushm
                          option.
  --db-popr               Restore state of Z80 registers from an earlier
                          --db-pushr option.

  --db-portr p[,m]        Read port 'p' and display the value. An optional 'm'
                          value if specified will be placed onto the MSB of the
                          port address, if 'm' is omitted 0 will be used.
  --db-portw=p,v[,v..]    Write value 'v' to port 'p'.

  --db-pushm=s,f          Save state of memory starting from address 's' and
                          finishing at 'f'. Only one level is allowed.
  --db-pushr              Save state of Z80 registers. Only one level is
                          allowed.

  --db-saveb=t,b,file     Saves bank memory type 't', bank 'b', to a file. All
                          banks that belong to type 't' will be saved if 'a' or
                          'all' is specified for 'b'.
                          See 'Bank t arguments' section near the end of this
                          help for more information.
  --db-savem=s,f,file     Save memory starting at address 's' and finishing at
                          'f' to a file.

  --db-setb=t,b,o,v[,v..] Set memory in bank type 't', bank 'b' at offset 'o'
                          with value(s) 'v'.
                          See 'Bank t arguments' section near the end of this
                          help for more information.
  --db-setm=a,v[,v..]     Set memory locations starting at address 'a' with
                          value(s) 'v'. The number of 'v' arguments is limited
                          to the argument size allowed in this build and by the
                          host system. The address wraps around to 0 when
                          moving past 0xffff.
  --db-setr=r,v           Set a Z80 register 'r' with value 'v'. The register
                          register values supported are:
                          af, bc, de, hl, ix, iy, pc, sp, a, f, b, c, d, e, h,
                          l, i, r and alternate registers rr_p and r_p.

  --db-step=lines         Step lines of instructions.  For continuous operation
                          pass 'c' or 'cont' and to stop pass 's', 'stop' or
                          '0' for lines.  To step over a CALL instruction, pass
                          'o' or 'over'.  To step out of the currently CALLed
                          function, pass 'x' or 'exit'.  Step out runs until
                          the instruction after the next RET instruction
                          (excluding nested CALLs).

  --db-trace=s,f          Trace only if PC is between addresses 's' and 'f'
                          inclusively. Default is trace any PC value.
  --db-trace-clr          Clear the value set with the --db-trace option.

  -z, --debug=args        Debugging mode options.

                          This option uses prefixed arguments. See the
                          'Prefixed arguments' section near the end of this
                          help for more information. The 'off' and 'on'
                          arguments may also be used without a prefix if a
                          single argument is supplied.

                          The arguments recognised are:
                          all     (-+) all output options.
                          alt     (-+) output the alternate and I, R registers.
                          count   (-+) use instruction counter in disassembly.
                          index   (-+) output the index registers.
                          memr    (+-) output memory pointed to by 16 bit reg.
                          regs    (+-) output the standard Z80 registers.
                          off     (+-) disables/enables debugging mode.
                          on      (-+) enables/disables debugging mode.
                          piopoll (+-) PIO polling when stepping.
                          step    (-+) start stepping.
                          step10  (-+) step * 10.
                          step20  (-+) step * 20.
                          trace   (-+) start tracing.
                          tstates (+-) output Z80 instruction t-states.

  --debug-close           Closes a debugging capture file if open.
  --debug-open=file       Create a debugging capture file.  This file will
                          capture the output from all options belonging to the
                          debugging group when open.  This option will first
                          close any open file before creating a new file.
                          This open option will not append and will create a
                          new file overwriting any file by the same name.

  --dump=addr             Set the initial dump address value when using the
                          dump commands. addr must be a valid Z80 address from
                          0 to 0xFFFF. The default address is 0.
  --dump-lines=n          Set the number of lines for a memory dump. The
                          default value is 8.
  --dump-header=x         Enables/disables the dump header. Default is enabled.

  --echo=x                Echo a string to stdout. The string may also contain
                          an environment variable.
  --echoq=x               Same as --echo option but echoes a quoted version of
                          the environment variable if any spaces are found.

  --find-count=n          Set the maximum number of matches possible when using
                          the --db-find* options. The default is 20.

  --modio=args            Module I/O debugging output.

                          This option uses prefixed arguments. See the
                          'Prefixed arguments' section near the end of this
                          help for more information.

                          The arguments supported are:
                          log     (-+) logs to ubee512_log.txt
                          raminit (-+) use bank numbers as DRAM init values.

                          These arguments turn on port debugging for modules:
                          all       (-+) all selections.
                          beetalker (-+) beetalker module.
                          beethoven (-+) beethoven module.
                          clock     (-+) clock speed change.
                          compumuse (-+) Compumuse module.
                          crtc      (-+) CRTC access.
                          dac       (-+) DAC module.
                          fdc       (-+) Floppy Disk Controller registers.
                          fdc_wtd   (-+) FDC show the track write data.
                          fdc_wth   (-+) FDC show the sector header info.
                          func      (-+) function module.
                          hdd       (-+) ST506 Hard Disk Drive registers.
                          ide       (-+) IDE Hard disk drive registers.
                          joystick  (-+) joystick module.
                          keystd    (-+) standard keys (6545) module.
                          keytc     (-+) TC keys (256TC/Teleterm) module.
                          mem       (-+) memory management module.
                          options   (-+) options module.
                          roms      (-+) ROMs module.
                          pioa      (-+) PIO A data.
                          piob      (-+) PIO B data.
                          piocont   (-+) PIO control and interrupts.
                          rtc       (-+) Real Time Clock.
                          tapfile   (-+) TAP file module.
                          ubee512   (-+) application loop.
                          vdu       (-+) Video Display Unit.
                          vdumem    (-+) access to VDU memory.
                          video     (-+) SDL and OpenGL video.
                          z80       (-+) unhandled Z80 port accesses.

  --regs=args             Register dump. Determines what registers will be
                          dumped when the EMUKEY+R key is pressed.

                          This option uses prefixed arguments. See the
                          'Prefixed arguments' section near the end of this
                          help for more information.

                          The arguments supported are:
                          all  (-+) all selections.
                          crtc (-+) CRTC6545 registers.
                          pio  (-+) PIO registers.
                          rtc  (-+) RTC registers.
                          z80  (+-) Z80 registers.

 Disk drives:

  --disk-create=file      This option will create a disk image using LibDsk
                          support as first preference or by using the built
                          in RAW disk image support. To keep the option
                          simple the last 2 '.ext' parts of the file name are
                          used to determine the disk format and type.
                          If the '.type' value is omitted then the disk is
                          assumed to be a RAW disk image.

                          The file format required is: 'filename.format.type'
                          Some examples of different types using DS40 as the
                          format are shown below:

                          raw  : filename.ds40
                          raw  : filename.ds40.raw
                          dsk  : filename.ds40.dsk
                          edsk : filename.ds40.edsk

  --hdd(n)=file           The --hdd(n) options allow emulation of WD1002-5
                          Winchester and floppy disk controller drives. n=0-2
                          are hard disk drives and n=3-6 are floppy drives.
                          file=file path for drive (n).

  --hdd3-close            close WD1002-5 floppy disk (1st)
  --hdd4-close            close WD1002-5 floppy disk (2nd)
  --hdd5-close            close WD1002-5 floppy disk (3rd)
  --hdd6-close            close WD1002-5 floppy disk (4th)

  --ide-a0=file           file path for emulator IDE primary master drive.
  --ide-a1=file           file path for emulator IDE primary slave drive.
  --ide-b0=file           file path for emulator IDE secondary master drive.
  --ide-b1=file           file path for emulator IDE secondary slave drive.

  -a, --image_a=file      file path for emulator floppy drive A
  -b, --image_b=file      file path for emulator floppy drive B
  -c, --image_c=file      file path for emulator floppy drive C
  -d, --image_d=file      file path for emulator floppy drive D

  --a-close               close core board floppy disk A
  --b-close               close core board floppy disk B
  --c-close               close core board floppy disk C
  --d-close               close core board floppy disk D

                          LibDsk usage:
                          If LibDsk is to be used to access a floppy drive then
                          file path may be 'A:' or 'B:' for Windows or a device
                          file for Unices. i.e. /dev/fd0 and /dev/fd1 on Linux.

                          General usage:
                          If a drive already has a disk open then the disk is
                          closed before opening a new one. Do NOT change disks
                          while the Z80 system is actively working on the
                          drive or has files open, changing disks requires the
                          same rules required by a Microbee to be observed.
                          i.e. type '^C' in CP/M 2.2 after changing disk(s).

                          Dynamically named RAW FDD and HDD images:
                          A dynamic RAW image is where the file extension is
                          used to specify the CHS and optionally the sector
                          size of a RAW disk.  The format is '.hdd-C-H-S' and
                          '.fdd-C-H-S'. It is assumed they are 512 sector size
                          unless a size is also specified, i.e. 'C-H-S-128'.

                          See 'File path searching' further on for detailed
                          information. The default area for disks is:

                          @UBEE512@\disks\

  --cpm3                  Used by 'rcpmfs' driver to inform it a CP/M 3 file
                          system is in use. Default CP/M version is 2. This
                          must precede each Disk drive for each Disk drive
                          that has a CP/M 3 file system.
  --dstep                 Informs LibDsk the next Disk drives option uses
                          double stepping to support 48tpi DD disks in a 96tpi
                          DD drive. This option must precede each Disk drive
                          option when LibDsk is required.

  --dstep-hd              Same use as the --dstep option except this is for
                          48tpi DD disks in 96tpi HD drives.

  --format=type           Determines the disk format type when using LibDsk.
                          Using this option will cause the next Disk drives
                          option to use the LibDsk driver. This option must
                          precede each Disk drive option when LibDsk is
                          required. Additional disk formats can be placed into
                          the local libdskrc file.

                          ds40 and ds80 formats will automatically make use of
                          the --side1as0 option. Use the ds401 and ds801
                          formats if this behaviour is not required. i.e. PC
                          formatted disks)

  --lformat               Lists all the LibDsk built in and additional disk
                          formats that are available.

  --ltype                 Lists all the LibDsk driver types that are available.

  --side1as0              Informs LibDsk the next Disk drives option uses a
                          disk that has physical side one sectors containing 0
                          in the sector headers. The FDC write track emulation
                          will force the side information in the sector header
                          to use the physical side value with this option.
                          This option is no longer required to read and write
                          disks that have this issue.

  --type=driver           Determines what LibDsk driver will be used for the
                          next Disk drives option. This option must precede
                          each Disk drive option when LibDsk is required, if
                          not then LibDsk will attempt to automatically detect
                          the driver type to use.

 Display related:

  --aspect=n              Set the display aspect when using an SDL video mode
                          for rendering, n=1 is 1:1,  default aspect 2:1 (n=2),
                          n may be set to 1 or 2. 1:1 scaling may be enforced
                          for some CRTC6545 display sizes'.

  -f, --fullscreen[=x]    Toggle state of full screen mode, the display
                          defaults to a window (use EMUKEY+ENTER to toggle).
                          If 'x' is specified then full screen mode can be set
                          with x=on or window mode set with x=off.

  -m, --monitor=type      Monitor type, if this option is not specified a
                          colour monitor is the default when emulating colour
                          and green if a monochrome model. <type> may be one
                          of the following:

                          a,  amber : amber monitor.
                          g,  green : green monitor.
                          w,  white : white monitor, white foreground on black
                                      background.
                          b,  black : black monitor, black foreground on white
                                      background.
                          u,   user : user's monochrome configuration.
                          c, colour : colour monitor.

                          Note: This option by itself does not force the
                          emulation into a standard model Microbee, it's use
                          simply determines what monitor type is connected
                          to the emulated Microbee.

  --mon-bg-x=level        Set the 3 user customised monochrome background
                          colours. x is the gun colour ('r', 'g', 'b'). The
                          level value is 0-255.
  --mon-bgi-x=level       Set the 3 user customised monochrome dual intensity
                          background colours. x is the gun colour
                          ('r', 'g', 'b'). The level value is 0-255. This
                          option is only for the Premium (alpha+) models for
                          dual intensity monochrome (see --dint).
  --mon-fg-x=level        Set the 3 user customised monochrome foreground
                          colours. x is the gun colour ('r', 'g', 'b'). The
                          level value is 0-255.
  --mon-fgi-x=level       Set the 3 user customised monochrome dual intensity
                          foreground colours. x is the gun colour
                          ('r', 'g', 'b'). The level value is 0-255. This
                          option is only for the Premium (alpha+) models for
                          dual intensity monochrome (see --dint).

  --rgb-nn-x=level        48 options to customise the Premium (alpha+) colours.
                          nn is the colour value (00-15), x is the gun colour
                          ('r', 'g', 'b'). The level value is 0-255.

  --video=x               Video initial start state. x=on to enable, x=off to
                          to disable. Default is enabled.

  --video-depth=x         Video depth. Default is 16 bits per pixel. Other
                          depths may improve or degrade performance, i.e. sound
                          quality. These values only apply to SDL rendering. x
                          may be one of the following:

                          8   : 8 bit colour.
                          8gs : 8 bit grey scale.
                          16  : 16 bit colour.
                          32  : 32 bit colour.

  --video-type=type       Video type. The default type used is SDL hw rendering
                          Other types may improve or degrade performance, i.e.
                          sound quality. <type> may be one of the following:

                          gl : OpenGL (textured) hardware rendering.
                          hw : SDL hardware rendering.
                          sw : SDL software rendering.

 On Screen Display (OSD):

  --osd=args              OSD configuration.

                          This option uses prefixed arguments. See the
                          'Prefixed arguments' section near the end of this
                          help for more information.

                          The arguments supported are:
                          all     (+-) all selections.
                          animate (+-) animate OSD window minimising.

  --osd-consize=x,y       Set the console dialogue size. The x,y values may
                          be passed in 3 ways using any combination of the
                          following:

                          n   : These values match the X and Y values as used
                                by the CRTC emulation.
                          n%  : A percentage of the CRTC display, values 1-100
                                percent are permitted.
                          max : Uses the maximum available area of the CRTC.

  --osd-conpos=x,y        Set the console position. The x,y values may be
                          passed in 3 ways using any combination of the
                          following:

                          n      : These values match the X and Y values as
                                   used by the CRTC emulation.
                          n%     : A percentage of the CRTC display, values
                                   1-100 percent are permitted.
                          center : Positions the console in the center of the
                                   display on the x or y axis.
                          left   : Positions the console to the left of the
                                   display (for x only).
                          right  : Positions the console to the right of the
                                   display (for x only).
                          top    : Positions the console at the top of the
                                   display (for y only).
                          bottom : Positions the console at the bottom of the
                                   display (for y only).

  --osd-cursor=n          Set the OSD console cursor flash rate and type, the
                          flash rate is in milliseconds, a value of 0 gives a
                          solid cursor.

  --osd-list              List all the built in OSD schemes supported.

  --osd-scheme=x          Set an OSD scheme, if not specified the 'default'
                          scheme is used. Any further options that makes
                          changes to a scheme will work on the currently
                          selected scheme. When changing schemes the console
                          size and position values are inherited from the
                          current scheme. The --osd-list option can be used
                          to list what schemes are available. Other values
                          are as follows:

                          default : Select Default scheme.
                          user    : Select User scheme.
                          reset   : Resets the console size and position
                                    native to the current scheme.

 Editing scheme colours:

                          The following options are used to modify colours in
                          an existing scheme, the operations are applied to
                          the currently selected scheme only. The OSD scheme
                          is broken down into 3 main sections consisting of
                          'buttons', dialogue' and 'widgets' with each one
                          broken down into further properties of 'main' and
                          'text'.  Each option parameter consists of 2 or 4
                          arguments separated with ','. The following table
                          describes the argument structure:

                          c,c,c,c : BGHL, BGLL, FGHL, FGLL.
                          c,c     : BG,   FG.
                          BG      : Background colour (RGB 0x123456).
                          FG      : Foreground colour (RGB 0x123456).
                          HL      : Highlight.
                          LL      : Lowlight.
                          x       : Do not set this colour (leave as is).

  --osd-setbtnm=c,c,c,c   OSD Button main colours.
  --osd-setbtnt=c,c,c,c   OSD Button text colours.
  --osd-setdiam=c,c       OSD Dialogue main colours.
  --osd-setdiat=c,c       OSD Dialogue text colours.
  --osd-setwidi=c,c       OSD Widget icon colours.
  --osd-setwidm=c,c,c,c   OSD Widget main colours. The title box has no
                          BG highlight value and always uses the LL value.
  --osd-setwidt=c,c,c,c   OSD Widget text colours. The title box has no
                          BG highlight value and always uses the LL value.

 OpenGL rendering:

  --gl-aspect-bee=n       The aspect value you want for the Microbee display.
                          This default value is 4:3 aspect (1.333) but may be
                          changed with this option. Don't use this to fix
                          monitor aspects, use --gl-aspect-mon for that.
                          Use a floating point value for n. i.e. 4:3 aspect
                          is 4/3=1.333.

  --gl-aspect-mon=n       This option overrides the monitor aspect ratio worked
                          out by the emulator. This should not be needed for
                          LCD monitors running in native resolution. The value
                          may be required if running a 4:3 CRT monitor with
                          non 4:3 resolution. Use a floating point value for n.
                          i.e. 4:3 aspect is 4/3=1.333.

  filter options:         The OpenGL filter settings provide sharp or soft
                          display rendering. One is provided for each display
                          mode. The value for the current mode can be toggled
                          with the EMUKEY+F hot keys. The values allowed are:

                          sharp : sharp display.
                          soft  : soft display.

  --gl-filter-fs=x        filter setting for full screen mode. (sharp)
  --gl-filter-max=x       filter setting for maximised window mode. (sharp)
  --gl-filter-win=x       filter setting for resizable window mode. (soft)

  --gl-max=x              Start up maximised if x=on, if x=off then start up in
                          a window or full screen mode depending on the use of
                          --fullscreen option. Default is off. This option is
                          currently not supported on Windows machines.

  --gl-vsync=x            Vsync: swap buffers every n'th retrace. x=off to
                          disable, x=on to enable. Default is enabled.

  --gl-winpct=n           The default window size on start up determined by a
                          percentage value from 5-100% of the desktop X
                          resolution. If this option is not used the window
                          X size is 50% of the desktop width.

  --gl-winpix=n           The default window size on start up determined by
                          the number of pixels between 50 and the desktop X
                          resolution. If this option is not used the window
                          X size is 50% of the desktop width.

 File related:

                          The file options are for use by the uBee512 support
                          tools. How these are used is entirely dependent on
                          the Z80 application accessing these values. See the
                          TOOLS.TXT file for detailed usage information.

  --file-app=name         String name of up to 255 characters. Default is an
                          empty string.
  --file-exec=n           Z80 address 0-65535 (0000-FFFF hex). Default is 0.
  --file-list=files       Host file path(s) of up to 255 characters. @UBEE512@
                          variable if used will have double quotation
                          characters added if any space characters are found.
                          Default is an empty string. This option may be used
                          repeatedly to build up an array of strings.
  --file-list-q=files     Same as --file-list option except the entire string
                          will have double quotation characters added. No
                          double quotation characters will be placed around
                          the @UBEE512@ variable. This option may be used
                          repeatedly to build up an array of strings.
  --file-load=addr        Z80 address 0-65535 (0000-FFFF hex). Default is 0.
  --file-run=name         String name of up to 255 characters. Default is an
                          empty string.
  --file-exit=x           Enables/disables the state of the flag value, x=on
                          to enable, x=off to disable. Default is enabled.

 Information output:

  -h, --help, --usage     Display help information on command line usage.

  --conio                 Switches on verbose console output for Windows port.
                          By default only fatal errors and some option's output
                          is sent to the console.

  --lcon                  List the [section] names found in the configuration
                          file.
  --lconw                 Same as --lcon option except uses a wide format.
  --lcons=n               Sets the list start point for --lcon and --lconw
                          options. Default value is 1.

  --version               Obtain the version number of uBee512 and other
                          components (z80, SDL) being used.

 Joystick emulation:

                          Joystick emulation requires the parallel port device
                          to be set to 'joystick',  this is not required if the
                          joystick is being mapped to keys. See --parallel-port
                          option.

  --js=n                  Joystick number to use, n=0 for first joystick. n=-1
                          to disable an existing setting.

  --js-axis=x             Joystick axis mapping to buttons. x=on to enable,
                          x=off to disable. Default is enabled.
  --js-axisb=n            Joystick axis buttons base number. The axis button
                          offsets are 0=up, 1=right, 2=down and 3=left. The
                          base number n is added to the offsets to generate a
                          button number. n may be any value from 0 to 255.
                          Default value is 0x80 (128).
  --js-axisl=n            Determines the thresh hold level for button
                          detection. n may be any value from 1 to 32767.
                          Default value is 3200.

  --js-hat=x              Joystick Hat mapping to buttons. x=on to enable,
                          x=off to disable. Default is enabled.
  --js-hatb=n             Joystick Hat buttons base number. The Hat button
                          offsets are 0=up, 1=right, 2=down and 3=left. The
                          base number n is added to the offsets to generate
                          a button number. n may be any value from 0 to 255.
                          Default value is 0x90 (144).

  --js-shift=n            Joystick button to be used as a SHIFT button. n may
                          0-127 or -1 to disable. When a button is pressed in
                          conjunction with the SHIFT button the button's value
                          becomes the sum of 256 plus the button's normal
                          value. Default value is 0x07 (7).

  --js-clear              Clear all Microbee joystick button settings.
  --js-mbee=x             Microbee joystick emulation control. x=on to enable,
                          x=off to disable. Default is enabled.
  --js-ACTION=n[,n..]     Associate joystick ACTION with button(s) 'n'. The
                          values for ACTION and the default values are:
                          up    : 0x80, 0x90.
                          right : 0x81, 0x91.
                          down  : 0x82, 0x92.
                          left  : 0x83, 0x93.
                          fire  : 0x00, 0x01, 0x0b.
                          play1 : 0x04, 0x08.
                          play2 : 0x05, 0x09.
                          spare : 0x02, 0x03, 0x06.

  --js-clist              List the command names available for joystick mapping.
  --js-klist              List the key names available for joystick mapping.
  --js-kbd=x              Joystick to Microbee keys mapping control. x=on to
                          enable, x=off to disable. Default value is enabled.
  --js-kb=n               Button n to be associated with last --js-kk=k option.
                          Values of n=256-511 are processed as shifted buttons.
                          The --js-kkb option is the preferred method.
  --js-kk=k               Microbee key to be mapped to a joystick button. See
                          --js-klist option for more information.
                          The --js-kkb option is the preferred method.
  --js-kkb=k,n[,n..]      Replaces --js-kk and --js-kb options. This option can
                          be used to associate multiple buttons to a single
                          key. Values of n=256-511 are processed as shifted
                          buttons. See --js-klist option for more information.
  --js-ksel=n             Select the joystick key set to use. n may be a value
                          of (0-255) or alternatively specify n as a character
                          from A-Z, the letter will be converted to numbers
                          0-25. Default selection is 0.
  --js-kset=n             Place the joystick keys into set n and make active.
                          There are 256 sets of joystick keys (0-255) that may
                          be used or alternatively specify n as a character from
                          A-Z, the letter will be converted to numbers 0-25.

 Model emulation:

                          See 'File path searching' further on for detailed
                          information. The default area for roms is:

                          @UBEE512@\roms\

  --basic=file            Used for defining 4, 8, and 16K BASIC ROM parts.
  --basica=file           Same as --basic option.
  --basicb=file           Used for 4, 8K and ppc85 ROM part B.
  --basicc=file           Used for 4K ROM part C.
  --basicd=file           Used for 4K ROM part D.

                          These --basicx options allows the ROM file image
                          specified to be used instead of the built in model
                          defaults for the BASIC ROM(s).

  --basram                The memory locations 0xA000-0xBFFF for ROM based
                          models defaults to ROM. This option will force this
                          8K area to SRAM emulation. The contents will contain
                          a typical SRAM pattern on start up,  it will not be
                          associated with a ROM image file.

  --charrom=file          Allows the character ROM file image specified to be
                          used instead of the built in predefined 'charrom.bin'
                          ROM.

  --col                   Enables colour emulation for standard models. This
                          option has no affect when emulating a Premium, 256TC
                          or Teleterm model. Defaults to an RGBrgb digital
                          monitor type when used.

  --col-type=n            Same as --col option except the monitor type may be
                          selected. n=0 selects RGB analogue, and n=1 selects
                          RGBrgb monitor emulation. Default is disabled. This
                          option has no affect when emulating a Premium, 256TC
                          or Teleterm model.

  --colprom=file          Use the file values to override the internal 82s123
                          IC 7 standard colour values. This option has no
                          affect when emulating a Premium, 256TC or Teleterm
                          model.

  --dint=x, --hint=x      Dual intensity monochrome emulation for Premium
                          (alpha+) models. x=on to enable, x=off to disable.
                          This is set to 'on' by default for the 256TC and
                          upgraded Premium models. This option has no
                          affect when emulating a standard model. The --hint
                          option name should not be used any more.

  --edasm=[r,]file        This option is identical to the --pak0 option. See
                          the --pak0 option for more information.

  --hardware=x            Enable/Disable emulation of various hardware
                          sections allowing variations in models.

                          This option uses prefixed arguments. See the
                          'Prefixed arguments' section near the end of this
                          help for more information.

                          The arguments supported are:
                          wd2793      (+-) WD2793 FDC emulation.
                          sn76489     (-+) SN76489 sound IC emulation
                                           (premium only).
                          sn76489init (-+) SN76489 sound IC emulation with all
                                           voices initially silenced
                                           (premium only).

  --hwflash=x             Hardware inverse and flashing video emulation for
                          Premium (alpha+) models using one of two possible
                          methods. x=on to enable (v4), x=off to disable, x=v3
                          enables using Premium version 3 main board flashing.
                          x=v4 may also be used instead of x=on for Premium
                          version 4 main board, 256TC and Teleterm models.
                          This is set to 'on' (v4) by default for the 256TC
                          and upgraded Premium models. This option has no
                          affect when emulating a standard model.

  --hwflashr=x            Set the video hardware flashing rate for Premium
                          (alpha+) models, the true rate is determined by
                          CRTC 6545 values (VSYNC). The default value is 320
                          milliseconds. x may be one of the following timer
                          values: 20, 40, 80, 160, 320, 640, 1280 or 2560
                          milliseconds. Alternatively a link setting may be
                          used, v3 and v4 boards differ for W63 and W64:

                          Link  v3    v4   (milliseconds)
                          w61   160   160
                          w62   320   320
                          w63   1280  640
                          w64   640   1280

  --lmodel                List the available model types.

  --lpen                  Enables the use of the 6545 Light pen keys emulation.
                          This is enabled by default for all models except for
                          the 256tc and Teleterm models.

  --model=type            Model type, if this option is not specified the p512k
                          model is emulated. The 'p' denotes a Premium
                          variation in a model. This option should be used
                          before any other options.

                          The following models are supported:
                          256tc  : Telecomputer 256k DRAM with FDC.
                          p1024k : Premium 1024k (Premium plus).
                          1024k  : Standard 1024k (Premium plus).
                          p512k  : Premium 512k (PJB upgrade of 128k).
                          512k   : Standard 512k (PJB upgrade of 128k).
                          p256k  : Premium 256k (PJB upgrade of 64k).
                          256k   : Standard 256k (PJB upgrade of 64k).
                          p128k  : Premium 128k DRAM with FDC.
                          128k   : Standard 128k DRAM with FDC.
                          p64k   : Premium 64k DRAM with FDC.
                          64k    : Standard 64k DRAM with FDC.
                          56k    : 56k APC (50W expansion for FDC).
                          tterm  : Teleterm (ROM).
                          ppc85  : Premium Personal Communicator 85 (ROM).
                          pc85b  : Personal Communicator 85 (ROM) later.
                          pc85   : Personal Communicator 85 (ROM).
                          pc     : Personal Communicator (ROM).
                          ic     : First 3.375 MHz CPU clock (ROM).
                          2mhz   : Original 2 MHz kit and first units.
                          2mhzdd : Dreamdisk @ 2 MHz CPU clock.
                          dd     : Dreamdisk @ 3.375 MHz CPU clock.
                          scf    : Standard Compact Flash (CF) core board.
                          pcf    : Premium Compact Flash (CF) core board.

  --mono                  Disables colour circuit emulation for standard models.
                          This option when emulating a Premium, 256TC or
                          Teleterm model has the same affect as --monitor=g.

  --netram                The memory locations 0xE000-0xEFFF for ROM based
                          models defaults to ROM. This option will force this
                          4K area to SRAM emulation. The contents will contain
                          a typical SRAM pattern on start up,  it will not be
                          associated with a ROM image file.

  --netrom=file           Allows the ROM file image specified to be used
                          instead of the built in model defaults for the NET
                          ROM.

  --pak(n)=[r,]file       The --pak(n) options allows the ROM file image
                          specified to be used instead of the built in model
                          default for the PAKn ROM 0 to 7 locations.
                          4K ROM images can be specified by using the optional
                          'r,' argument. 'r' may be ROM 'a' or 'b'. The 'b'
                          ROM is only loaded if the 'a' ROM is 4K in size.

  --pakram=n              The PAK n location will use SRAM instead of ROM
                          emulation. The contents will contain a typical SRAM
                          pattern on start up,  it will not be associated with
                          a ROM image file. n may be any PAK number from 0-7.

  --pcg=n                 Premium (alpha+) model option that sets size of PCG
                          RAM to be emulated. n is the size of the PCG memory
                          in Kilobytes and can be any even value between 2 and
                          32. 256TC, Premium and Teleterm models are 16K,
                          upgraded Premium models are 32K. This option has no
                          affect when emulating a standard model.

  --piob7=signal          Determines what signal is used for PIO port B bit 7.
                          The default value depends on the model emulated.
                          The source values are: rtc, vsync, net, and pup.

  --port58h               Enables 3rd party WD1002-5/WD2793 (port 0x58) support
                          to allow selecting the required drive interface.

  --rom1=file             Allows the ROM file image specified to be used
                          instead of the built in model default for the boot
                          ROM. This ROM is only used by all FDC models.
  --rom2=file             Allows the ROM file image specified to be used
                          instead of the built in model default for ROM2. This
                          ROM is used by all DRAM FDC models, except for the
                          256TC.
  --rom3=file             Allows the ROM file image specified to be used
                          instead of the built in model default for ROM3. This
                          ROM is used by all DRAM FDC models, except for the
                          256TC.

  --rom256k=file          Allows the 256K ROM file image specified to be used
                          instead of the built in model default for the 256K
                          ROM. This ROM is used by some 3rd party designs.
                          Set file to 'none' to disable the 256K ROM image.

  --sram=n                ROM models option that sets size of static RAM to be
                          emulated. n is the size of the SRAM memory in
                          Kilobytes and can be any value between 0 and 32.
                          Default value is 32.
  --sram-backup=x         Enables (x=on) or disables (x=off) CMOS battery
                          backup emulation for CMOS RAM. Default is enabled.
  --sram-file=file        Use this file name instead of the default model
                          'model.ram' file name for the CMOS battery backup
                          emulation.
  --sram-load=x           Enables (x=on) or disables (x=off) CMOS battery
                          backup emulation file loading on start-up for ROM
                          based and 56k models, Default is enabled.
  --sram-save=x           Enables (x=on) or disables (x=off) CMOS battery
                          backup emulation saving when exiting the emulator
                          for ROM based and 56k models, Default is enabled.

  --sys=name              Defines a system name,  this will be appended to some
                          files so that different operating systems using the
                          same model can still have unique names for certain
                          files. By default this name contains nothing. An
                          example is the loading and saving of RTC values. By
                          default for a p128k model this would be 'p128k.rtc',
                          by defining name to be 'mysys' would then use
                          'p128k-mysys.rtc' for the file, the emulator inserts
                          the hyphen character.

  --vdu=n                 Premium (alpha+) model option that sets size of VDU
                          RAM to be emulated. n may be 2 or 8. The VDU RAM
                          size determines the number of screen, attribute and
                          colour RAM banks. Default is 2K. Don't use this
                          option to increase to 8K unless you understand the
                          problems associated with it.

 Microbee mouse emulation:

  --mouse=x               Microbee mouse emulation. x=on to enable Microbee
                          mouse emulation on start-up. Default is 'off'.

 Parallel printer emulation:

                          Parallel printer emulation requires the parallel port
                          device to be set to 'printer'. See --parallel-port
                          option.

                          See 'File path searching' further on for detailed
                          information. The default area for printer is:

                          @UBEE512@\printer\

  --print=file            Printer output to file,  the output is not modified.
                          If an open printer file is already in use then that
                          file will be closed first before creating the new
                          printer file.
  --print-close           Closes a currently open printer file. This allows the
                          file to be accessed externally without exiting the
                          emulator.

  --printa=file           Printer output to file,  the output is converted to
                          ASCII decimal. If an open printer file is already in
                          use then that file will be closed first before
                          creating the new printer file.
  --printa-close          Closes a currently open ASCII printer file. This
                          allows the file to be accessed externally without
                          exiting the emulator.

 Parallel port device selection:

  --parallel-port=device  Select the external parallel port peripheral device
                          to be emulated on PIO port A.  The default device is
                          'printer'. The following devices are supported:

                          none      : no device.
                          printer   : parallel printer.
                          joystick  : joystick. (not required for mapped keys)
                          beetalker : Microbee BeeTalker speech emulation.
                          beethoven : Microbee BeeThoven sound synthesiser.
                          dac       : 8 bit audio DAC.
                          compumuse : EA Compumuse sound synthesiser.

 Compumuse options:

                          Compumuse emulation requires that the parallel port
                          device be set to 'compumuse'. See the
                          --parallel-port option.

  --compumuse-init        Silences the emulated sn76489 when the Compumuse is
                          initialised.
  --compumuse-clock=n     Sets the Compumuse's clock frequency, in Megahertz.
                          Valid values for n are 1, 2, 4. Default value is 2.

 Quickload support:

  --ql-list=file          List description contained in a quickload file.
  --ql-load=file[,x]      Load a quickload file, an optional 'x' will cause
                          the code to be executed once loaded.
  --ql-x                  Execute the quickload file in memory.

  --qla-arc=file          Specify a quickload archive file to be used for
                          further operations. Only ZIP archives are currently
                          supported. Any archive currently open will be closed
                          first.
  --qla-dir=file|*[,+v]   The entire archive directory will be listed if '*'
                          is specified for file or a single file within the
                          archive matching 'file' may be specified.  An
                          optional verbose argument of '+v' may be specified
                          for more information.
  --qla-list=file|*       The entire archive directory will be listed if '*' is
                          specified for file or a single file within the
                          archive matching 'file' may be specified.
  --qla-load=file[,x]     Load file from the current quickload archive, an
                          optional 'x' will cause the code to be executed
                          once loaded.

 Real Time Clock (RTC) emulation and time:

  --century=n             This value can be used to correct the century date
                          used in ROMs. Changes are temporary and are made to
                          the image(s) in memory only. An MD5 value will be
                          used to identify what loaded ROM images need
                          modifying. The value of n is expected to be in BCD
                          format. The century '20' should use n=0x20 (hex) or
                          n=32 (dec). The following ROMs with matching MD5s
                          will be modified in memory:

                          256TC v1.15: md5=13ddba203bd0b8228f748111421bad5f
                          256TC v1.20: md5=24d6682ff7603655b0cbf77be6731fb0
                          256TC v1.31: md5=4170a8bb9495aa189afb986c1d0424a4

  --rtc=n                 Real Time Clock (RTC) emulation. n=1 to enable, n=0
                          to disable. The following models use RTC by
                          default: 256tc, p1024k, 1024k, p512k, 512k, p256k,
                          256k and tterm.

 Serial port emulation:

  --baud=rate             Set serial communications baud rate for both TX and
                          RX. A value from 1 to 38400 is allowed. Default
                          rate is 300 baud. If Individual baud rates are
                          required for TX and RX then use the --baudtx and
                          --baudrx options instead. This value must match the
                          Microbee serial application's value.

  --baudtx=rate           Set serial communications baud rate for TX only. A
                          value from 1 to 38400 is allowed. Default rate is
                          300 baud. This value must match the Microbee serial
                          application's value.

  --baudrx=rate           Set serial communications baud rate for RX only. A
                          value from 1 to 38400 is allowed. Default rate is
                          300 baud. This value must match the Microbee serial
                          application's value.

  --coms=port             Serial communications port for emulation of RS232.
                          On Unices specify a device, on Windows specify the
                          com port number. No serial communications will be
                          emulated if this option is not specified. If a
                          serial port is already open then that port will be
                          closed first before opening a new serial port.

  --coms-close            Closes the RS232 serial port if currently open.

  --datab=bits            Set serial communications number of data bits. A
                          value from 5 to 8 is allowed. Default value is 8
                          data bits. This value must match the Microbee
                          serial application's value.

  --stopb=bits            Set serial communications number of stop bits. A
                          value from 1 to 2 is allowed. Default value is 1
                          data bits. This value must match the Microbee
                          serial application's value for TX.

 Sound emulation:

  --sound=method          Determine the method used for sound,  the default
                          method is 'prop':

                          off    : sound is turned off
                          prop   : sound is proportional to CPU clock frequency
                          normal : sound rate forced as if 3.375 MHz CPU clock

  --snd-freq=f            Set the sound sampling rate, f may be a value from
                          5512 to 176400 Hz. Default frequency is 44100 Hz.
  --snd-hq                Sets high quality sound. How well this works will be
                          dependent on the host platform. This option has the
                          same effect as setting all these values:
                            --snd-samples=2048.
                            --snd-freq=88200.
  --snd-mute=x            Sound mute, use to start the emulator with the sound
                          muted until enabled. x=on to enable, x=off to
                          disable. Default is off.
  --snd-samples=n         Sets the SDL callback data size. n must be a power of
                          2. Values from 1 to 32768 are allowed. Default is
                          1024 samples.
  --snd-volume=l --vol=l  Set the sound volume level. A level of 0 to 100% is
                          allowed. Default is 45%.

 Speed related:

  --clock=f               Set the Z80 clock frequency for emulation in MHz.
                          Standard emulation frequencies are 3.375 and 2.0
                          MHz. All other frequencies are classed as 'hacking'.
                          3.375 MHz is the default clock frequency. Frequency
                          is entered as a floating point number.

                          The highest frequency possible is determined by the
                          host platform. As the value increases to the point
                          where uBee512 can no longer regulate the Z80
                          execution rate the frame rate will decrease (slower
                          screen update periods).

  --clock-def=f           Set the Z80 clock frequency for emulation in MHz when
                          the uBee512 API restore function is called. Default
                          frequency is 3.375 MHz.

  --frate=fps             Frame rate, an integer value between 1 and 1,000,000
                          is allowed. Default is 50 FPS.

  --maxcpulag=n           This is the maximum time the Z80 CPU emulation is
                          allowed to get behind before 'catch up' is bypassed
                          for the currently lagged cycles. A very high value
                          for n will cause the 'catch up' mode to always be in
                          affect,  using a value of 0 for n will effectively
                          disable this feature and act like 2.5.0 and earlier
                          versions. Default value is 250ms.

  --speedsel=n            CPU speed selection emulation. n=1 to enable, n=0
                          to disable. The following models are enabled by
                          default: 256tc, p512k, 512k, p256k, 256k.

  -t, --turbo[=x]         Turbo mode, executes Z80 code as fast as possible.
                          Without this option the emulation attempts to keep
                          Z80 CPU execution to match the CPU clock value.
                          If 'x' is specified then turbo mode can be set with
                          x=on or off with x=off. This option is intended for
                          'hacking' and code development use. There are much
                          faster methods if more speed is required. (see the
                          README file)

  --vblank=method         Vertical blanking method to be employed. This is
                          only intended for 'hacking' when experimenting with
                          turbo mode and/or high CPU clock speeds. It is not
                          required or even recommended to be used if 3.375 MHz
                          or 2 MHz emulation is desired.

                          0 : 50 Hz VBLANK rate derived from Z80 cycles and is
                              proportional to the CPU clock frequency.
                          1 : 50 Hz VBLANK rate derived from the host timer.

                          When running in turbo mode then setting the <method>
                          equal to 1 will ensure that a VBLANK rate of 50Hz
                          will be used. Without this, key repeating may be
                          too fast.

  -x, --xtal=f            Old non preferred options to set the Z80 clock
                          frequency. Use --clock option instead.

  --z80div=n              Determines the number of Z80 blocks emulated per z80
                          frame. This value allows the polling rate to be
                          increased or decreased. The polling rate per second
                          is the product of the frame rate (--frate) and this
                          value. The value of n may range from 1 to 5000. On
                          versions prior to 2.7.0 this value was 1. Default
                          value is 25.

 Tape port emulation:

                          See 'File path searching' further on for detailed
                          information. The default area for tapes is:

                          @UBEE512@\tapes\

                          WAV and TAP files are supported and the input and
                          output method can be mixed.

  --tapei=file            Tape input from a WAV file. If an open tape input
                          file is already in use then that file will be closed
                          first before opening the new tape input file.
  --tapei-close           Closes a currently open tape input file. This allows
                          the file to be accessed externally without exiting
                          the emulator.
  --tapei-det=value       Optional input high and low detection percentage for
                          simulating tape input hysteresis threshold levels.
                          This value if specified is used in place of the
                          internally set value of 0%.

  --tapeo=file            Tape output to a WAV file. If an open tape output
                          file is already in use then that file will be closed
                          first before creating the new tape output file.
  --tapeo-close           Closes a currently open tape output file. This allows
                          the file to be accessed externally without exiting
                          the emulator.

  --tapesamp=frequency    Tape output sample frequency in Hz. Default is
                          22050 Hz.

  --tapevol=level         Tape output wave file volume level. A level of 0 to
                          100% is allowed. Default is 15%.

  --tapfile-list=file     List all the DGOS tape file names contained in the
                          TAP file.
  --tapfilei=file         TAP file input and output options, these work in the
  --tapfileo=file         same fashion as that described for the tape WAV file
  --tapfilei-close        options. No initial tape rewind is required for TAP
  --tapfileo-close        files.

 ## Variables
                           The --varset option may be used to create variables.
                          These variables are pre-configured:

  UBEE_USERHOME           User's home path on Unices, or the directory
                          containing the ubee512 exe on Windows systems.
  UBEE512 or ubee512      Path to the ubee512 account.
  UBEE_VERSION            Emulator version.
  UBEE_HOST               Host system (UNIX or WIN).
  UBEE_SYS_MAJOR          On Unix systems this will be 'UNIX' On Windows
                          systems it contains one of the following:
                          win9x_me, nt4, nt5 or nt6. Both systems will use
                          upper case for the variable value.
  UBEE_SYS_MAJOR_VAL      Windows OSVERSIONINFOEX dwMajorVersion member value.
  UBEE_SYS_MINOR          On Unix systems this will be the value of the
                          uname.sysname member. On Windows systems it contains
                          one of the following: w95, w98, me, nt4_ws,
                          nt4_server, w2000, xp, server_2003, vista, w7, w8,
                          w8.1 or w10. Both systems will use upper case for
                          the variable value.
  UBEE_SYS_MINOR_VAL      Windows OSVERSIONINFOEX dwMinorVersion member value.
  UBEE_MODEL              Microbee model selected for emulation.
  UBEE_RAM                Amount of main memory (kb) for the emulated model.

 Time and Date            These variables are normally used to form other
                          variables, see TD variable usage in 'ubee512rc'.

  SS                      Seconds. (00-59)
  MM                      Minutes. (00-59)
  HH                      Hours. (00-23) 
  DD                      Month day. (01-2x/3x) 
  mm                      Month. (01-12) 
  YYYY                    4 digit year. (1900-20xx)
  YY                      2 digit year. (00-99)
  ww                      Week day Sun-Sat. (0-6)
  ac                      Week day capitalised. (Sun-Sat)
  al                      Week day lower case. (sun-sat)
  au                      Week day upper case. (SUN-SAT)

 ## Arguments
   Integer arguments:
  Integer values may be entered using Decimal, Hexadecimal or Octal notation.
  For Hexadecimal input a leading '0x' or 0X' must precede the actual value.
  i.e. '0x12', 0x1234'.  For Octal input a leading '0' must precede the actual
  value. i.e. '012', '01234'. The default input notation is decimal.

  Floating point arguments:
  Floating point values may be entered using Decimal or Hexadecimal notation
  in the same way as for Integer arguments.

  Prefixed arguments:
  Prefixed arguments must commence with a '+' or '-' character, a '+' prefix
  enables while a '-' prefix disables.

  The prefixes supported by each argument will be shown in brackets along
  side it, i.e. (+-). The first prefix shown represents the default state.

  Additional arguments may be declared in the same option. A '+' prefixed
  argument may be negated by using a '-' prefixed one.

  Bank t arguments:
  These values are used by some of the debugging options that operate on
  banks of memory.

  ## 't' type     RAM type
    att          attribute memory.
  col          colour memory.
  pcg          PCG memory.
  scr          screen memory.
  mem          DRAM memory.
  vid          all video memory.

 ## File path searching
   Path slash characters:
  Forward or back slashes may be used in file paths irrespective of the
  program being run under Unices or Windows environments when slash
  conversion is enabled. See --slashes option. Unices will see '\' as an
  escape sequence when used on the command line and also when found in
  configuration files and slash conversion is disabled.

  Files to be opened:
  Existing files will first be searched for in the current directory, if the
  path is not found a second search in the default directory will take place.
  For the second search the file path specified will be appended to the default
  directory path. The second search is not carried out if a '\', '.\', or
  '..\' are the first characters of the path or a ':' character is used under
  Windows.

  Files to be created:
  Files to be created will be placed into the default directory unless a path
  to another location is specified by using a '\', '.\', or '..\' as the
  first characters of the path or a ':' character is used under Windows.

If you have any new feature suggestions, bug reports, etc. then post a new
topic at www.microbee-mspp.org.au

## Some sample command lines
Show the help information on command line usage.
>ubee512 -h

Boot the boot.dsk image found in the default location.
>ubee512

Boot the boot.dsk image found in the path specified. Use forward slashes on
Unices.
>ubee512 -a \path\otherboot.dsk

Boot a 128K system with A and B images
>ubee512 -a myboot128k.dsk -b mydisk-ds40.dsk

For the 'micro defender' game we must emulate a standard monochrome model or
if emulating an alpha+ model use the monochrome option and disable the half
intensity emulation.  The second example uses '-mw' to force a white on a
black background monitor.
>ubee512 -a mybootdisk.dsk --mono --hint=off
>ubee512 -a mybootdisk.dsk -mw --hint=off

Boot the default boot image in full screen mode.
>ubee512 -f

Boot the default boot image in turbo and full screen mode.
>ubee512 -t -f

Boot the default boot image with the sound off.
>ubee512 --sound=off

Boot the default boot image with the sound volume set to level 10.
>ubee512 --vol=10

Boot the default boot image with a Z80 clock frequency set to 2 MHz.
>ubee512 --clock=2

Boot the default boot image, use a tape input wave file.
>ubee512 --tapei=mytape.wav

# Specifications
## WAVE FILE FORMAT
uBee512 uses The Canonical WAVE File Format.

Here are some links about it:
http://www.lightlink.com/tjweber/StripWav/Canon.html

I used this as my reference material:
http://ccrma.stanford.edu/courses/422/projects/WaveFormat/

Files created by uBee512 are:
- PCM: 1 (no compression)
- Channels: Mono (single channel)
- Sample rate: can be specified using --tapesamp option
- Bits per sample: 8 (unsigned)

Files read by uBee512 must conform to:
- PCM: 1 (no compression)
- Channels: specification dependent (only the first channel data is used)
- Sample rate: specification dependent
- Bits per sample: 8, 16 or 32

# 3rd Party tools
Several library extraction tools to work under CP/M can be found on some
MBUGnnn.ARC disk archives.

## lbrate Library Tool
A library extraction tool (lbrate) and an de-archiving tool for arc files
(nomarch) is available for Unices here:
http://rus.members.beeb.net/index.html

I have cross compiled lbrate for win32 by changing the CC entry in the make
file from CC=GCC to CC=i386-mingw32-gcc then running i386_mingw32-strip on
it to reduce the size of the executable down.  It should also be possible to
compile under Windows and GCC without any changes necessary to the Makefile.

The cross compiled 'lbrate.exe' can be found here:

http://www.microbee-mspp.org.au/forum

## cpmtools (patched)
Modified binary releases of cpmtools.  The modifications allow Microbee
disks to be accessed.  This release also has LibDsk support compiled in. 
Direct floppy access under Linux and Windows is possible.  Another feature
added to the patch is the addition of CP/M file location reporting of
Side/Cylinder/Sector.  See the ChangeLog and README.PATCH for more
information.

Windows and Linux Binaries and patch files are available found here:
http://www.microbee-mspp.org.au/repository

Check under the 'patched_cpmtools' directory.

# Frequently Asked Questions (FAQ)
Q: I'm having some problems using uBee512,  where can I get some help ?
A: There is a topic devoted to uBee512 on the Microbeee MSPP forum located
   here: http://www.microbee-mspp.org.au/forum. You can post questions there.

Q: I have a "boot.dsk" image in the correct location but the emulator
   reports something like (Windows example): fdc_loaddisk: Unable to open
   c:\Program files\ubee512\disks\boot.dsk
A: This is most likely caused by the "boot.dsk" file set as read only.  This
   file must be writeable.  In Windows explorer right click on the file and
   select the properties option, then uncheck the Read-only flag.

Q: How often can I expect to see new releases ?
A: As this project is under active development expect releases every 3-6
   months or less, but this may vary due to any problems that may be
   encountered along the way and also other commitments.

   Bug fix releases will normally only occur if I believe it has a large
   impact on the performance of the software so may be held over to the next
   minor or major release version.  I may release unofficial bug fix
   releases from time to time.

Q: How can I receive notifications of a new release ?
A: Creating a Google alert may work.

Q: The display shows up as all white when using OpenGL video mode.
A: Most likely this is because you are using a video card driver that does
   not support OpenGL. Install the latest video drivers for your video
   hardware.  See 'OpenGL Rendering' under the 'Display' section for more
   information.

Q: Using OpenGL video mode makes emulation very slow, why ?
A: OpenGL requires a native driver for your video that has OpenGL support.
   If this is not the case then OpenGL is emulated causing it to be slow.

Q: When using a joystick the keys on the keyboard stop working and/or the
   joystick does not work as expected.
A: Set the joystick to non-analogue mode or calibrate the joystick. See the
   joystick section for further details.

Q: Can I install uBee512 on a flash drive and run on different Windows
   systems directly from it ?
A: Yes, uBee512 does not make a registry entry if installed from the ZIP
   file so it is quite portable and should run on W98/Me/XP/Vista.

Q: The sound is very slow and sounds strange,  what's the problem ?
A: This problem now appears to be resolved, make sure you are using the
   latest version (2.7.0 or later).

Q: The CP/M system hangs on boot up even after replacing the disk image with
   a known good one.
A: Try deleting the @UBEE512@/rtc/rtc-file associated with the model being
   emulated as this may have become corrupted.  A new one will be created
   when the emulator exits.

Q: The LOCK key does not work correctly under win32 or x11.
A: The LOCK key behaviour can be fixed by using either the --lockfix-win32
   or --lockfix-x11 options.

Q: When I use the turbo mode option, pressing a key causes multiple keys to
   be displayed in very quick succession.
A: Use the --vblank=1 option when using the turbo mode option.

Q: I don't see any console output for some things when running under
   Windows.
A: Under Windows console output goes to stdout.txt.  All console output can
   be seen in another cmd Window by using the --conio option.

Q: It's a bit of chore having to type in long command lines with the options
   I desire, how can this be made easier ?
A: Use the configuration file,  you can create the entries that you require
   then simply run with: ubee512 mysetup.  You can also create batch files
   in Windows or script files under Unices that contain your favourite start
   up methods.  Alternatively create desktop links with the command options
   included.

# Acknowledgements
Thanks to all those that are assisting or have assisted in one way or
another in the past with the emulator's development.

Thanks to the Microbee community for providing technical information,
feedback and ideas, and ALPHA testers.  A lot of the information and ideas
received have gone back into improving the emulator.  Thanks also to the
authors of z80ex, and other libraries for their assistance.

Thanks to the nanowasp v0.22 release by David G. Churchill. This project was
forked from it.

# Links
- Microbee utilies.  This site provides some tools to assist in archiving
  Microbee ROMs and disks and some other software I have written for the
  Microbee.

  http://www.microbee-mspp.org.au/repository

- This site has a forum devoted to the Microbee and provides a lot of useful
  information and software for registered users.

  http://www.microbee-mspp.org.au/forum

- emuControlCenter (ECC) An emulator GUI front end that has support for
  uBee512 and provides a nice interface to play Microbee games:

  http://www.camya.com/eccblog/

- The Unofficial CP/M Web site
  http://www.cpm.z80.de

- Walnut Creek CDROM,  contains a lot of Microbee and CP/M stuff, see the
  'beehive' and 'mbug' directories:

  http://z80cpu.eu/mirrors/oldcomputers.dyndns.org/cdrom/cpm

- Other sites:
  http://www.digitalresearch.biz/CPM.HTM
  http://www.classiccmp.org/dunfield/
  http://www.seasip.demon.co.uk/Unix/LibDsk/
  http://www.seasip.demon.co.uk/Cpm/index.html
  http://www.znode51.de/indexe.htm

# Projects by this author

## uBee512
An emulator for the Microbee Z80 ROM, FDD and HDD based models.

http://www.microbee-mspp.org.au/repository

## uBeeDisk
A tool for converting disks/images from one to another with
auto detection options for Microbee disks.

http://www.microbee-mspp.org.au/repository

## z80em86
A Z80 CPU emulator coded in Intel 86 assembly language.

http://www.cpm.z80.de/source.html
http://www.gaby.de/z80/z80emu.htm

# Contact
If you have any new feature suggestions, bug reports, etc. then please post
in the appropriate forum topic at http://www.microbee-mspp.org.au/forum

For bug reports please provide the following information:
1) Version number of the uBee512 emulator.
2) The platform it was running on, for example if running on Windows then
   state if W95, W98, Me, W2000, XP, Vista, W7, W8, W8.1, W10, etc.  Same
   for Linux, state the actual Linux distribution used and version.
3) SDL version used if known. (use --version option)
4) What uBee512 distribution package was used for the installation.
5) Path used for the installation.
6) Command line start up options used (cut and paste if possible)
7) Description of the problem.

Enjoy!
