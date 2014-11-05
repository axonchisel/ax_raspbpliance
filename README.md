
# Ax_Raspbpliance - Raspberry Pi Raspbian Web-Based Appliance Ansible Playbook

v0.8 - 2014-11


## Project Overview

### Goal

  - Formalize and automate creation of permanent embedded custom Raspberry Pi web-based "appliance" 

### What it is

  - An automated playbook for use with Ansible configuration management tool
  - Documentation and usage instructions

### How it works

  - Input:
  	- One [Raspberry Pi](http://www.raspberrypi.org/) mini computer
  	- One SD card (4 GB Class 4 or higher recommended) with Raspberry Pi [NOOBS or Raspbian](http://www.raspberrypi.org/downloads/) installed
  	- Wifi connection info
  	- URL to any web page
  - Process:
  	- ax_raspbpliance playbook with [ansible-playbook](http://docs.ansible.com/playbooks_intro.html) configuration management tool
  - Output:
  	- Hardened read-only power-cyclable Raspberry Pi configured to boot up directly to your web page in full screen kiosk mode Chromium browser with disappearing cursor and screen saver disabled.

*Read more here about [our goal, philosophy, and mission statement](./docs/philosophy.md).*



## Project Status

  - 2014-11 - working beta, tested on RPi B+.
  - More work planned including non-NOOBS support, Chrome browser tweaks, ...

*See a list here of [planned upcoming work](./docs/todo.md).*

*See our [developer's guide](./docs/dev.md) for those wishing to help.*


## Instructions

### A Tale of Two Computers

You will use a control machine (e.g. your laptop) to download a Raspberry Pi OS install, prep an SD card, and finally run the configuration management tool [Ansible](http://docs.ansible.com/) to remotely configure your Pi (or multiple Pis simultaneously). On your actual Pi, you will do as little as possible.  

Overall you should only have to run ~2 short commands and kick back while the computers do all the hard work.


### Initial Setup and OS Install

These generic steps should take 1 - 10 minutes depending on your familiarity, experience, and net speed.

  1. **Create an SD card** with a fresh Raspbian install, optionally using NOOBS

    - *Read more here on [deciding between and installing NOOBS and/or Raspbian](./docs/raspbian.md).*

  2. **Install the OS** on your Pi (with keyboard, monitor), accepting all defaults.

    - *NOOBS keyboard shortcuts: `K` for keyboard, `i` for install.*
    - *raspi-config keyboard shortcuts: `TAB`, `TAB`, `ENTER` to finish.*

  3. **Connect your Pi** to ethernet and start it up.

    - *Read more here on [setting up without ethernet and general connectivity issues](./docs/netconnect.md).*

  4. **Push your SSH key** from your control machine to your Pi, e.g.

        $ ssh-copy-id pi@raspberrypi

    - *Read more here on [SSH keys, ssh-copy-id tool, connectivity, and more](./docs/ssh-copy-id.md).*


### Unattended Ax_Raspbpliance Process

Here's where the magic starts. Expect about 10 - 20 minutes while the Pi is automatically configured.

  1. Make sure you've **installed Ansible** on your control machine.

    - *On OS X: `$ brew install ansible`*

  2. Make sure you're in this project's **`sys` directory** where you see the file `RUN PLAYBOOKS FROM HERE.md`.

        $ cd ax_raspbpliance/sys

  3. Copy the `myvars-example.yml` file to `myvars.yml` and **customize vars** with:
    - wifi connection info
    - URL you want the Pi to start on
    - optional settings for graphics mode, overclocking, ...

  4. **Run the playbook** from your control machine:

        $ ansible-playbook plays/ax_raspbpliance.yml -e "@myvars.yml"

    If your Pi wasn't reachable as `raspberrypi` or you have a numeric IP address, you may specify that on the command line like:

        $ ansible-playbook plays/ax_raspbpliance.yml -e "@myvars.yml" \
                                                     -e 'ansible_ssh_host=192.168.1.99'

  5. **Wait** approximately 10 - 20 minutes while your Pi is completely configured remotely!


### Result

Upon completion your Raspberry Pi will be configured to start up and automatically connect to the wifi network and launch the web page you specified in a full screen kiosk-mode modern browser, and to support safely disconnecting power at any time without "shutting down"...  A web-based appliance!

*Review here a more [detailed technical deep dive into actual changes](./docs/details.md).*

## Compatibility

Ax_Raspbpliance has been tested and found compatible with:

  - Raspberry Pi models
  	- A
  	- B+
  - Raspbian Linux versions
  	- Raspbian 7 (wheezy) (~2014)
  - NOOBS versions
  	- NOOBS 1.3.10 (~2014)
  - Ansible versions
  	- Ansible 1.7.2 (~2014)



------------------------------------------------------------------------------

Ax_Raspbpliance - Copyright (c) 2014 AxonChisel.net
