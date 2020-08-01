
# Special packages asus-rog with Debian 10
## Wifi
Download [http://ftp.us.debian.org/debian/pool/non-free/f/firmware-nonfree/firmware-iwlwifi_20161130-5_all.deb](https://drive.google.com/file/d/1m4nEecT6fVXnOe-qYyj3v6VhL2gdmdey/view?usp=sharing) and install with `dpkg -i`


## Graphics
after configure the non-free repositories
```bash
apt-install nvidia-detect
$ nvidia-detect
nvidia-driver
$ sudo apt install nvidia-driver
```

## Back light of the keyboard
See https://askubuntu.com/a/644420/678974 

For turn on/off: (1,__2__,3 for on)
```bash
sudo echo 2 | sudo tee /sys/class/leds/asus::kbd_backlight_1/brightness
sudo echo 0 | sudo tee /sys/class/leds/asus::kbd_backlight_1/brightness
```
or try https://askubuntu.com/a/810715/678974



