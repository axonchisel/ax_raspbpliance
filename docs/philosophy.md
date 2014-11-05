
# Ax_Raspbpliance - Goals, Philosophy, Mission Statement


## Overview

### Project Goal

  - formalize and automate a process for creating a Raspberry Pi web-based "appliance"

### Project Status

  - 2014-11 - working alpha, tested on RPi B+.
  - Needs more work including non-NOOBS support (see [TODO](./todo.md))


### What is an "Appliance"?

#### An "appliance" must...

  - run unattended 24/7 for years
  - be able to recover from random errors by simply power cycling

#### An "appliance" must not...

  - suffer from SD card corruption or capacity issues over time
  - suffer from SD card corruption due to improper shutdown
  - require any shutdown at all other than pulling power


### Read-only

Because fragile SD card corruption is at the heart of so many problems, many of these goals are achieved by shifting as much of the system as possible into read-only mode and keeping dynamic data in memory only.

It is also core to our philosophy of an "appliance" that it be immutable, and that any requisite persistence be handled explicitly.


### Formalize & Automate

The "formalize and automate" portion of the goal is addressed by the use of [Ansible](http://docs.ansible.com/), a fantastic (and free) IT automation tool.

Rather than describing the steps an admin should take to achieve these goals, we construct a "playbook" that is run from a command and control computer (such as your desktop PC) to remotely configure a new Raspberry Pi.

This greatly simplifies and accelerates the setup process, resulting in a tested, documented, flexible, powerful, and easy way to go unattended from factory stock Raspberry Pi to appliance mode in minutes.


### Why not just offer a turnkey OS distribution?

Rather than providing an out-of-the-box appliance distribution that can be installed directly, we choose to provide a reproducible computer and human friendly version controlled series of steps that can take an existing distribution and convert is accordingly. 

Our approach works with many variants of Raspbian, likely including ones not yet released, and ensures that end users know exactly what they're getting without having to wade through hundreds of megabytes of unknown content.

But these choices also do not preclude release of appliance distributions, as such could be created easily with these scripts!  (And you are welcome to do so as long as you give credit and retain copyright notices, as we release these scripts under the liberal MIT license).





------------------------------------------------------------------------------

*Return to the [README](../README.md)*
    
------------------------------------------------------------------------------

Ax_Raspbpliance - Copyright (c) 2014 AxonChisel.net
