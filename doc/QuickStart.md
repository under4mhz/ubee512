********************************************************************************
                                    uBee512

         An emulator for the Microbee Z80 ROM, FDD and HDD based models.

                     Copyright (C) 2007-2016  uBee

                              Quick Start Guide
********************************************************************************

# I just want to get straight into it!
Okay, for those that don't want to or don't have time to read the
documentation then these instruction will get you started as quickly as
possible.

If you are just interested in playing some games using game disk images then
see the "Games disk" section below or if you want to kow what ROMs are
required for a specific model emulation see the "Model emulation" section
below:

## Games disk
1. Install ubee512 (Windows users: use the EXE installer is the easiest)

2. Download and install ROMs:
   ROMs are available from the site shown below.
   (NOTE: location and names are subject to change by the site administrator)

   http://www.microbee-mspp.org.au/repository/
   ---> Goto the 'ROMs' directory and read the README file.

   Download these two ROMs and copy to the 'ubee512\roms' directory:

   charrom.bin
   rom1.bin

3. Download a games disk:
   Disk images are available from the site shown below.
   (NOTE: location and names are subject to change by the site administrator)

   http://www.microbee-mspp.org.au/repository/
   ---> Goto the 'Disks' directory and download the games demo disk file.

4. Place the games disk into the 'ubee512\disks' directory.  Make note
   of the disk_image_file_name.

5. Under a CLI (DOS/CMD Prompt) CD to the directory where ubee512 is installed.

6. Enter the following at the command prompt for first time initialising, it
   will report that this is a new version of uBee512 and exit, you can
   ignore the message and continue to the next step:

   ubee512

7. Enter the following at the prompt to play the games on the disk:

   ubee512 -a disk_image_file_name

8. When you're done exit the emulator by pressing the 'END' key and confirm exit
   when prompted.

## Model emulation
1. Install ubee512 (Windows users: use the EXE installer is the easiest)

2. Download and install ROMs:

   The model being emulated will determine what ROMs are required. See the
   'roms.alias' file and the header sections for the model to be emulated. 
   These will describe the ROMs required.

   Where and how to obtain specific Microbee model ROMs is beyond the scope
   of this document.  Various Microbee ROMs are available from
   http://www.microbee-mspp.org.au/ but requires a login then reading and
   understanding the topics under the following forum:

   "MSPP site information"
   http://www.microbee-mspp.org.au/forum/viewforum.php?f=28

# All users
For those that want to know how to install and use uBee512 in more detail
see the INSTALL file found in the documentation directory.
