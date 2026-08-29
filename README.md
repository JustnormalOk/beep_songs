# beep_songs
Beep songs that come from the PC speaker

# NOTICE
1. These commands that I only use are `os.system`, to actually run the command.
2. Since new computers these days might not include the buzzer, you might actually need a 4-pin speaker header for this case to play the sound.
3. The beep function I provided may need sudo for this.

# REQUIREMENTS
1. You need to install 'beep' module for your Linux distribution for this to work, because these kinds of code only uses "beep" to make that buzzer sound from your PC or laptop.
2. Python module
3. Your computer must have a buzzer supported
4. A PC speaker (inside the motherboard)

# INSTRUCTIONS 

*Note that this part is only for Arch!!*

## Install beep module for your Linux distro
1. `sudo modprobe pcspkr` - this loads it temporarily 
2. `echo "pcspkr" | sudo tee /etc/modules-load.d/pcspkr.conf` - this loads it on boot
3. `sudo pacman -S beep` - installs beep

*This part sets up the instructions for beep to play it on the onboard speaker instead*

1. `sudo nano /etc/udev/rules.d/70-pcspkr-beep.rules` - create a rule file for it
2. Just paste this exact line, `ACTION!="remove", SUBSYSTEM=="input", ATTRS{name}=="PC Speaker", ENV{DEVNAME}!="", TAG+="uaccess"`, and then save it, by pressing Ctrl + O, press Enter, and Ctrl + X to exit.
3. Reload the udev rules and restart module `sudo udevadm control --reload && sudo rmmod pcspkr && sudo modprobe pcspkr` 

## Installation

1. Open the terminal, then go to the desired folder (like this folder!; e.g: `cd /home/<yourcomputerusername>/Downloads/beep_songs-main`).
2. After that pick one of the songs you'd like. (YOU WILL NEED PYTHON FOR THIS!!!), by typing `python3 badapple.py` or `python3 wantyougone.py`

# FEATURES
2 songs I have made so far, include:
- Bad Apple 
- Want You Gone - By Aperture Science Psychoachoustic Laboratories

(this is actually my first time, making repos, thanks, please appreciate it, thank you)

