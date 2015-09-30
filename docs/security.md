
# Ax_Raspbpliance - Security Protections and Vulnerabilities


## Overview

This document contains a brief overview of security protections and vulnerabilities of Ax_Raspbpliance as deployed in the field.


## Protections

| Protection  | Implications |
| ------------- | ------------- |
| SSH by key only | Prevents remote attacks on weak passwords. |
| Default `pi` user password deleted | Prevents plugging in keyboard and logging in to common account. |


## Vulnerabilities

| Vulnerability  | Implications |
| ------------- | ------------- |
| Physical access to SD card  | SD card may be removed and viewed.  Only known vulnerability is presence of wifi password in cleartext (useful for easy post-install config).  Of course a malicious user modifying contents of SD card and re-inserting may introduce any possible vulnerability.  |
| Physical access to USB ports | Keyboard and/or mouse may be plugged in.  May gain access to login screens on alt TTYs, but no login will be possible.  May review log messages in scrollback buffer, but not useful.  May reboot device or leave screen in non-kiosk mode, easily fixed with reboot. |



------------------------------------------------------------------------------

*Return to the [README](../README.md)*

------------------------------------------------------------------------------

Ax_Raspbpliance - Copyright (c) 2015 AxonChisel.net
