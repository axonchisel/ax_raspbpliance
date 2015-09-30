
## The `ansible.cfg` file in this directory is required!


### Ansible will only see it if you run playbooks from this directory like:

    $ cd this_directory
    $ ansible-playbook plays/name-of-playbook.yml



### Command Usage


##### Run the main playbook

    $ ansible-playbook plays/ax_raspbpliance.yml

##### Run supplemental playbooks

    $ ansible-playbook plays/inspect.yml
    $ ansible-playbook plays/remount-rw.yml
    $ ansible-playbook plays/remount-ro.yml
    $ ansible-playbook plays/reboot.yml



------------------------------------------------------------------------------

*View [README](../README.md)*
    
------------------------------------------------------------------------------

Ax_Raspbpliance - Copyright (c) 2015 AxonChisel.net
