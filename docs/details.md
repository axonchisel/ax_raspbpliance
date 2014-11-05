
## Technical Details


### What happens during installation

The `ansible-playbook` command on your control machine will show progress as it runs.

Along the way your target machine will be modified, including:

  - system software updated
  - firmware updated
  - a number of large packages (e.g. Java, Wolfram Engine) will be removed to free ~800 MB disk space
  - some new packages are installed
  - a user created and set to auto-run a kiosk mode browser on a specific URL
  - disk mounts set to read-only
  - various subsystems disabled, including logging
  - areas requiring disk writes shifted to tmpfs RAM disks


There may be several points where your Pi is rebooted.

At some point you will be notified that the wifi is configured and you can unplug your ethernet cable.


### Special user `tempo`

There is now an additional user (default `tempo`) intended as primary application user.  This user's home directory is stored in a RAM disk, so all data is reset every time the power is cycled.  This user is the one who runs the web browser session.

Because the root file system is now read-only, the default `pi` user itself has a non-writeable home directory which will cause various problems (including not being able to startx).  You may log in as `pi` and `sudo su tempo` if you like.



### Other playbooks

Several utility playbooks are available:
    
    $ ansible-playbook plays/ax_raspbpliance.yml

    $ ansible-playbook plays/remount-rw.yml
    $ ansible-playbook plays/remount-ro.yml
    $ ansible-playbook plays/reboot.yml


The `ansible.cfg` file in the same directory as `RUN PLAYBOOKS FROM HERE.md` is important. Ansible will only see it if you run playbooks from that directory like:

    $ cd proper_directory
    $ ansible-playbook plays/name-of-playbook.yml -e "@myvars.yml"




------------------------------------------------------------------------------

*Return to the [README](../README.md)*
    
------------------------------------------------------------------------------

Ax_Raspbpliance - Copyright (c) 2014 AxonChisel.net

