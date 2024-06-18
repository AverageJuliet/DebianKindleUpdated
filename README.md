# Installing Debian on your Kindle

# Update (2024): This project is no longer deprecated. I have no idea who the hell is gonna use this but its fixed!

# things you need installed beforehand 
1. a JB on your kindle
2. kterm
3. mental insanity ngl

Now that you have a terminal, you will be able to install the Debian chroot. 
Here's where it gets complicated. First, you need to generate a Debian image appropriate for your device. 
Use `MakeImage.sh` to do this. Run the script on a Linux system to generate the image. If you do not have access to a Linux system, then skill issue.

Now, move the `debian.ext3` file on to your Kindle's root directory. You're almost there.
Once you have moved `debian.ext3`, you need to move the `RunDebian.sh` script and the `UpdateInitScript.sh` script as well as `RunBeforeDebian.sh`

on to your Kindle. Now you can run them. Do this by typing 
`cd /mnt/us` and then `./RunDebian.sh --root` on your Kindle. You are now root on your Kindle!

Then, hit `CTRL-D` on your Kindle until you see `[US]$` or `[US]#` 
you are now back in your Kindle's terminal. Type `./RunBeforeDebian.sh` on your Kindle to setup mountpoints and install the `debian command/. 
Now, you should be able to type `debian` in the Kindle's terminal to access Debian. 
If you need root access (to install sudo, add users, etc) type `debian --root` to start Debian as root. 

You should now have a working Debian install. 

Finally, you need to setup Debian (IF YOU HAVE A PREGENERATED IMAGE YOU CAN SKIP THIS STEP)
First, type `debian --root` to enter Debian as root.
then type `adduser <USERNAME>` replacing `<USERNAME>` with your name.
Next, type `apt-get install sudo`.
Then, type `adduser <USERNAME> sudo` replacing `<USERNAME>` with your name and follow the prompts.
Finally, hit `CTRL-D` until you see `[US]$` and type `debian`.
Login with your username and password.
Finally, type `echo alias "sudo"="sudo -S"`.

-Enjoy!

Open an issue in the [Issue Tracker](https://github.com/KatHamer/DebianKindle/issues) if you encounter any issues, or
PM me on Reddit (u/dylanhamer13) if you need help with any of the instructions.

Thanks for the support, 
Kat
or send me a friend request on discord if you run into an issue somewhere
averageemogirl
juliet (new maintainer) 
