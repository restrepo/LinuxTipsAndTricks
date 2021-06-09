# Terminal
## How to turn off the beep only in bash tab-complete
Editing `/etc/inputrc`
```bash
set bell-style none
```
## Google Drive
```bash
rclone mount drive:/ rclone --daemon
fusermount -u /home/restrepo/rclone
```

# Desktop
## Locales configuration
Search Latinamerican keyboar in English locale. 
To configure for several flavors of Spanish and English use:
```bash
# dpkg-reconfigure locales
```
and choose `es_ES.UTF-8`, `es_ES.UTF-8`, and `us_US.UTF-8`

In Gnome go to `Settings → Region & Language`

# Devices
## bluetooth headset connects but not showing in sound settings
See [here](https://askubuntu.com/a/1301449/678974): The proposed solution thatis to set option ControllerMode to bredr in file `/etc/bluetooth/main.conf`
```bash
# Restricts all controllers to the specified transport. Default value
# is "dual", i.e. both BR/EDR and LE enabled (when supported by the HW).
# Possible values: "dual", "bredr", "le"
#ControllerMode = dual
ControllerMode = bredr
```
When you changed the option restart Bluetooth service
```bash
sudo systemctl restart bluetooth
```


