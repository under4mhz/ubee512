# uBee512 Build and Install Instructions
The information here details how to install binaries for Windows and Linux
systems and how to build and install from source.

## Software distributions
The latest source and binary distributions are available from:

http://www.microbee-mspp.org.au/public_repository

The "n.n.n" is the version number:

ubee512-n.n.n.tar.gz       : Source files
ubee512-n.n.n-win32.exe    : Binary installer for Windows
ubee512-n.n.n-win32.zip    : Binary files in ZIP format for Windows
ubee512_n.n.n_i386.deb     : Binary package for Ubuntu (Debian)
ubee512-n.n.n-2.i386.rpm   : Binary package for RPM based distributions
ubee512-n.n.n.tgz          : Binary package for Slackware
ubee512-n.n.n-portable.zip : Binary package combining Windows and Unix

# Installation
For Windows systems the binary installer EXE, binary ZIP, or the Portable
binary ZIP distribution may be used.  The later is a combination of Windows
and Unix binaries.

All binaries have z80ex, LibDsk, zlib, bz2lib and zziplib statically linked
in.  Linux binaries have other dependencies that must also be met.

On Windows the emulator may be installed to any location you want including
a USB drive, if installing to a systems area then you may need to have
administration rights to install and run the program.

## EXE file
1. If you have an existing installation then save the current libdskrc file
   if this has been customised.  This file if it exists will be found in the
   share directory.
2. If you have a previous installation that used the installer you should
   remove this first with the add/remove software found in the control
   panel.  This should not delete any files you have placed into the
   installed location but it is recommended that the files be backed up
   first anyway.
3. Run the installer and follow the directions.
4. To access floppy drives on Windows 2000 and above requires a special
   floppy driver to be installed. This is available from here:
   http://simonowen.com/fdrawcmd/
5. Follow the install instructions under 'ALL SYSTEMS'.

## WIN32 ZIP file
1. If you plan on installing over an existing installation then save the
   current libdskrc file if this has been customised.  This file if it
   exists will be found in the share directory.
2. Unzip the Windows ubee512-n.n.n-win32.zip binary distribution to a
   location you wish to use.  If you have a previous installation then you
   can just unzip over the top of the other.
3. To access floppy drives on Windows 2000 and above requires a special
   floppy driver to be installed. This is available from here:
   http://simonowen.com/fdrawcmd/
4. You can create a desktop link to the emulator with some options if you
   don't want to run from a command line.
5. Follow the install instructions under 'ALL SYSTEMS'.

## UBUNTU DEB (DEBIAN)
Binary package for Ubuntu.

1. Use a package installer of your choice. To use the dpkg installer from a
   command line:
   $sudo dpkg -i ubee512_n.n.n_i386.deb
   or from the desktop double click on the deb file from 'File browser'
2. Follow the install instructions under 'ALL SYSTEMS'.

## RPM (general)
The RPM package should install on most RPM based linux distributions. 

1. First you may like to do a test install as root, this won't actually
   install any files but may show any potential problems before installing:
   # rpm -i --test ubee512-n.n.n-2.i386.rpm
   To do the real install as root:
   # rpm -i ubee512-n.n.n-2.i386.rpm
2. Follow the install instructions under 'ALL SYSTEMS'.

## TGZ (Slackware)
Binary tar compressed package intended for Slackware or any Linux x86
installation, this contains the installed directory tree (./usr/...) and
files.

1. Install the package as root:
   #installpkg bee512-n.n.n.tgz
2. Follow the install instructions under 'ALL SYSTEMS'.

## PORTABLE ZIP (Windows/Unix binary(s))
Binary package intended for portable R/W media installations (i.e. USB flash
drives). Start-up scripts provided allows running Windows or Unix versions of
uBee512 from the same drive without the need to install under the host
system.  The Unix build of uBee512 may also be run from some 'Live CDs'.

1. If you plan on installing over an existing installation then save the
   current libdskrc file if this has been customised.  This file if it
   exists will be found in the share directory.
2. Unzip the ubee512-n.n.n-portable.zip binary distribution to a location
   you wish to use.  If you have a previous installation then you can just
   unzip over the top of the other.
3. As a user under Windows or Unix and under a command line change directory
   to the installed location.
4. Follow the install instructions under 'ALL SYSTEMS'.

## UNICES FROM SOURCE (Linux/FreeBSD)
1. If you have not built and installed the package you need to do that
   first, see the section 'Building from sources'.
2. Make sure you are logged in as a normal user.
3. Follow the install instructions under 'ALL SYSTEMS'.

## ALL SYSTEMS
1. Run the ubee512 emulator.  The first time this occurs a windows message
   (or text to stdout in Unix) will be displayed with some information. Some
   directories and files will be created in your home account.  It will then
   exit. (Windows will ask you to confirm first).
2. Copy the required disk images to the installed program directory
   @UBEE512@\disks\ (see DISK IMAGES below)
3. Copy the required ROM images (see ROM IMAGES in README file)
4. Optional is to place tape wave files in @UBEE512@\tapes\
5. A ubee512rc will have been created if no previous file by that name
   existed, this file may be edited to allow settings to be customised. 
   (see CONFIGURATION FILE in the README file).  If you want to use OpenGL
   video rendering mode then the --video-type=gl option must be specified.
6. If running from a console prompt from any location you will need to add a
   path for the system to find ubee512.

## DIRECTORY AND FILE STRUCTURE
The following directories and files will be created in the home account when
uBee512 is run for the first time or when installing from the ZIP or
installer applications/scripts:

Directories:
disks           default location for disk images.
doc             documentation for uBee512, license information, etc.
files           default location for Microbee files.
images          contains uBee512 icons, etc.
printer         default location for printer output emulation.
roms            default location for ROMs.
rtc             used by uBee512 for storing RTC values per model.
share           contains libdskrc disk definitions file.
tapes           default location for tapes in/out.
tools           contains support tools (may be empty on Unices)

Files:
ubee512_ver.id  contains the current version ID string and settings.
ubee512rc       default configuration file.
disks.alias     default disk aliases file.
roms.alias      default ROMs aliases file.
roms.md5        default ROMs MD5 file.

Windows only:
configs         contains sample configuration files.
ubee512.exe     uBee512 executable file.
SDL.dll         SDL Dynamic Link Library file.

Unices only:
.ubee512        ubee512 account in home directory.
/usr/local/bin/ contains ubee512 binary.
/usr/local/share/ubee512 contains default ubee512 configuration files,
documentation, tools source code, etc.

## RUNNING FOR THE FIRST TIME
Each time uBee512 is run a check is made for the presence of the version
identification file (ubee512_ver.id) and the contents. If the ID version is
older than the current emulator running or if not found then a console
message will be displayed with information, the user should follow the
instructions before running the emulator again.

Older versions of the emulator (from v3.0.0) may co-exist if desired without
affecting the account or seeing the install message re-appearing.

Other files and directories will be created if not found. ubee512rc,
roms.alias, disk.alias and roms.md5 files will be created from default files
if these are not already found in the uBee512 directory.

# Building from sources
The information provided here is for a Unix (Linux or FreeBSD) like build
environments, the Makefile detects the host OS type and will set up values
accordingly.  At present Linux, FreeBSD and Darwin systems can be detected. 
Other systems will use a default section.  The win32 port of the emulator
can be optionally cross compiled:

You will need to have a GCC build environment set up for the native build
and if you want to cross compile you will also need mingw and install the
SDL and z80ex and any other optional libraries for mingw.  Change the
MINGW_PREFIX value in the Makefile to suit your system.

z80ex, LibDsk and OpenGL support is pre-set to be compiled in but can be
modified in the Makefile or by using parameters to make.

## uBee512 dependencies
These must be compiled and installed on the build system if not already
present.  Some are optional and may be configured by passing options to the
Makefile (always do a make clean between changes):

zziplib (optional):
This is required for quickload ZIP file support.
http://zziplib.sourceforge.net/

Under a Debian based system install:
sudo apt-get install libzzip-dev

zlib (optional):
This is needed by zziplib and is required for quickload ZIP file support and
optionally for LibDsk file compression.
http://www.zlib.net/

Under a Debian based system install:
sudo apt-get install zlib1g-dev

bz2lib (optional):
This is required by LibDsk for file compression support.

Under a Debian based system install:
sudo apt-get install libbz2-dev

LibDsk (optional):
LIBDSK is a library for accessing discs and disc image file. Ensure 'zlib'
and 'bz2lib' development packages are installed before building LibDsk for
file compression to be included.

http://www.seasip.demon.co.uk/Unix/LibDsk/

OpenGL (optional):
Normally a development package is supplied for the video card driver on Unix
platforms.  For Windows cross compiling there should already be the required
files that comes with Mingw.

SDL:
Normally a pre-built development package is supplied or available for Unix
platforms. For Windows cross compiling the SDL source package must be cross
compiled first.

Under a Debian based system install:
sudo apt-get install libsdl1.2-dev

z80ex:
Z80~Ex is the portable ZiLOG Z80 CPU emulator designed as a library.
http://sourceforge.net/projects/z80ex/

Others:
To compile for FreeBSD and Mac OS X you need to be on a native system.  You
should check the Makefile FreeBSD/Darwin sections to see if it is correct
for your version.

On Unices generally, it appears that you must have a minimum KDE
installation for SDL to work.

## z80ex
z80ex must be compiled and installed on your system before you can compile
uBee512.  The instructions below are for z80ex v1.1.19

Please see notes in the 'z80ex_typedefs.h' file (if distributed) in the
'src' directory.  It is intended that this is a temporary solution only to
be able gain access to Callback functions.  The notes will explain why that
file is there and caveats concerning it's use.

Building for different platforms:

## Linux and FreeBSD
For Linux and FreeBSD systems this should compile fine with a make and then
a make install as root.  Make sure the ENDIANNESS is set to the correct type
in the Makefile for your architecture before doing a make.

make

as root:
make install

## Macintosh Intel OS X and PPC OS X
For Macintosh PPC architecture edit the Makefile and set the ENDIANNESS to
WORDS_BIG_ENDIAN, and for Intel to WORDS_LITTLE_ENDIAN.

make
sudo make install

## LibDsk
LibDsk will be built into uBee512 unless a command line build option is used
to disable it.  LibDsk is not essential but does provide extra features
which are recommended.

Note: Since uBee512 v4.3.0 Dreamdisk emulation has been included. LibDsk
v1.2.1 will need to be patched to allow Dreamdisks to be accessed.  This may
not be needed on a later version if available.  Dreamdisk images can still
be accessed using the built in DSK and RAW disk image support.

The patch also greatly improves the 'remote' type serial speed (including
USB serial).  Patches and how to apply notes are located in
'ubee512-n.n.n/patches/libdsk-1.2.1x-ubee.patch.zip'

## Building uBee512
Untar the source distribution into a work area logged in as a normal user:

$ tar -xzf ubee512-n.n.n.tar.gz    (n.n.n is the version number)
$ cd ubee512-n.n.n/src

There are compile options for each platform that can be changed in the
Makefile or by specifying options on the command line. See the Makefile for
further details.

A 'make clean' MUST be run first if any options have been changed between
builds.

$ make

or on FreeBSD

$ gmake

If you want to cross compile the windows version:
$ make win

## Install the files
As root:
# make install

or if you use sudo (ubuntu) you could use:
$ sudo make install

## Un-install the files
As root:
# make uninstall
