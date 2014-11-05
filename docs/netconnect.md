
## Setting up when no ethernet is avaialable and diagnosing connectivity


### No Ethernet available - Wifi instead

When no physical ethernet is available, you can still manually configure wifi on your new Pi once it boots successfully into your Raspbian install by hand by logging in, running `startx`, then using the Wifi configuration GUI.

Once you complete that, make sure your control computer can see your Pi and continue the installation.



### Make sure your control machine can see your Pi

Run this from your control PC you will be configuring the Pi from:

    $ ping rasperrypi


### Ping fails?  On hostnames, DNS, and numeric IPs...

Raspbian by default attempts to register its hostname `raspberrypi` along with its DHCP lease. If your DHCP server and name resolver communicate properly, you should be able to identify and see your new Pi by this name. Consider yourself lucky if this works for you! Frequently DNS cache, solar flares, and gremlins prevent this.

If you can't ping `raspberrypi`, then you must determine the actual IP address your Pi obtained via DHCP by either viewing your router/DHCP server status table or directly from the Pi.

When the Pi boots up, it should display its IP address as one of the last things printed.  If not, you can also log in to the Pi (default username `pi`, password `raspberry`) and look for the IP address in the output after running the command:

    $ ifconfig

Once you find the IP address, try to ping from command computer again by using the numeric address instead of name, e.g.:

    $ ping 192.168.1.77

If this works, then you can use the numeric IP address in place of hostname for the rest of the installation.  Or optionally set another mapping from host name to IP address (beyond the scope of this guide).


------------------------------------------------------------------------------

*Return to the [README](../README.md)*
    
------------------------------------------------------------------------------

Ax_Raspbpliance - Copyright (c) 2014 AxonChisel.net
