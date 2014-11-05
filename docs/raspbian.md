
## Generic NOOBS + Raspbian Installation


### Download and create a new SD card for your Raspberry Pi installation.
    
You want stock Raspbian running on your Pi.  You have two choices for your SD card:

  - [Install NOOBS](http://www.raspberrypi.org/help/noobs-setup/) + Raspbian:

    - easy to create the SD card (just format FAT and copy files from a .ZIP)
    - recovery/reinstall mode very easy and helpful when testing, especially with larger "offline" version of NOOBS

  - [Install Raspbian directly](http://www.raspberrypi.org/documentation/installation/installing-images/README.md):

    - more technical to install (must write disk image directly to SD card)
    - slightly faster boot
    - more difficult for users to damage system by accessing NOOBS recovery



### With your Pi off, connect to it:

  - monitor/display
  - keyboard
  - your new SD card
  - (mouse optional but not really needed)


### Boot your Pi.  You should see a rainbow splash.

#### Using NOOBS?

The NOOBS graphical interface will come up.
    
Change the language and keyboard first (`L` and `K` shortcut keys).

Install Raspbian (`i` shortcut key).

Wait for the initial Raspbian installation to complete.

This can take approximately 10-15 minutes.

When finished, you'll see a small dialog pop up asking you to confirm reboot.
Click the OK button, or press ENTER.


### Upon Raspbian first boot, you'll see a lot of text fly by as Linux starts up.

A utility called `raspi-config` will automatically load on this first boot.

We don't need to change anything here, and if we do it may be overwritten by subsequent config steps anyway, so just click FINISH, or press `TAB`, `TAB`, `ENTER`.


### You have a factory fresh Raspbian installation.

We haven't done any customization yet, but we're about to!

------------------------------------------------------------------------------

*Return to the [README](../README.md)*

------------------------------------------------------------------------------

Ax_Raspbpliance - Copyright (c) 2014 AxonChisel.net
