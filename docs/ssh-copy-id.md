
## SSH Keys, ssh-copy-id, connectivity, DNS, and more...


### Set up your command and control machine

You'll be running the configuration from your own PC, acting as control computer connecting remotely to the Raspberry Pi.

The setup script will expect to use key-based SSH login. So you need to have a few things set up already on your computer.



### Make sure you have SSH keys

If you've ever SSH'd anywhere, you already have your own SSH keys generated.

If not, you'll have to create some.  There are many guides online on this topic, but the basic summary is you'll execute something like this on your computer to create a local private/public key pair:

    $ ssh-keygen -t rsa


### Make sure you have the "ssh-copy-id" program installed

This program is used on your control computer to push your keys to other computers, allowing you to login without passwords in the future.

On OS X with Homebrew, you can install this program like:

    $ brew install ssh-copy-id

Technically you don't need this program if you're comfortable manually placing your public key on your new Pi.  But in that case, you probably don't need these instructions.



### Copy your control machine SSH pub key to the new Pi

This will allow you to ssh to the Pi without entering your password. Run (on your control machine):

    $ ssh-copy-id pi@raspberrypi

If you had to use a different hostname or numeric IP, you can specify that instead:

    $ ssh-copy-id pi@HOSTADDR

You'll have to enter the password for the `pi` user, which is by default `raspberry`.


### SSH errors

SSHing to a new server will likely result in one of two responses.

  1.  You will either be asked to accept a new RSA key fingerprint, to which you should reply "yes".

  2.  Or you will get an error regarding possible DNS spoofing, with:

          WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!
      
      This error would happen if your computer previously connected to the same IP address but saw a different public key fingerprint. This is not uncommon since you just re-installed a new OS.

      In this case, just open your control computer's "known hosts" file and remove the lines referencing your Pi, either by host name or by IP address, and try again. They'll probably be near the bottom.

      You can typically edit the file from the command line like:

          $ nano ~/.ssh/known_hosts



------------------------------------------------------------------------------

*Return to the [README](../README.md)*
    
------------------------------------------------------------------------------

Ax_Raspbpliance - Copyright (c) 2014 AxonChisel.net
