
# Ax_Raspbpliance TODO


## OPEN ISSUES

This is a work in progress.  Some open issues and notes are listed here.


### Chromium Settings

  - Lots of errors currently being logged related to writing to profile.
  - Probably need to pre-create an empty profile for Chromium to save data into.
  - Incognito mode might prevent attempts to write to disk, but we might want to pre-seed user data in the future, e.g. cookies, saved passwords, etc.



### "Chromium didn't shut down correctly"

  - This ugly error comes up on browser startup sometimes, including after some ALT-F4 quit.
  - There is a way to address this by using sed to rewrite a log file to make Chrome think it was OK.


### Issue with 'none' file type from fstab

  - Error message on boot re /var/tmp fstab mount: Unknown filesystem type 'none'




## UNDER CONSIDERATION


### Security

  - firewall configuration


### Automatic Reboots

  - Optional configure to automatically restart daily at specific time.


### Background health checks

  - Consider including a URL in initial config, cron pings every 15 minutes.


### Other TTYs

  - Disable additional ttys in /etc/inittab?
  - Makes it diffficult to debug, so do by variable config (default disable them)

### sysvinit vs. systemd

As of 2015-10, Raspbian 7.8 is still based on the classic sysvinit startup system.  However there is a trend in Linux toward systemd, and it's likely that Raspbian will go this way soon.

The main autoexec integration of Ax_Raspbpliance is via rc.local, and this will likely need to be revisited if and when systemd replaces sysvinit.  It's possible that simply hooking rc.local to execute on boot will be an easy fix.






------------------------------------------------------------------------------

*Return to the [README](../README.md)*

------------------------------------------------------------------------------

Ax_Raspbpliance - Copyright (c) 2015 AxonChisel.net
