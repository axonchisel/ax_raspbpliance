
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



### NOOBS

  - For a true appliance we don't want NOOBS coming up and giving end users ability to reimage the disk.
  - So adapt this playbook and test it out with a straight Raspbian install.
  - But we want it to work with NOOBS too, so make sure it works on both ways (with NOOBS, without).
  - Possibly use gathered facts re devices (presence of p5, p6?) to set_fact on using_noobs=True or False.
  - Only difference should really be in fstab J2 which should handle both ways.





## UNDER CONSIDERATION


### Security

  - firewall configuration
  - disable SSH password logins


### Background health checks

  - Consider including a URL in initial config, cron pings every 15 minutes.


### Other TTYs

  - Disable additional ttys in /etc/inittab?
  - Makes it diffficult to debug, so do by variable config (default disable them)





------------------------------------------------------------------------------

*Return to the [README](../README.md)*

------------------------------------------------------------------------------

Ax_Raspbpliance - Copyright (c) 2014 AxonChisel.net
