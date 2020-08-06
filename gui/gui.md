# GUI Apss
## Openboard
### With desktop write in Gnome
See https://github.com/OpenBoard-org/OpenBoard/issues/209#issuecomment-488025177
```sh
$ flatpak install https://flathub.org/beta-repo/appstream/ch.openboard.OpenBoard.flatpakref
```
and run with
```sh
$ flatpak run ch.openboard.OpenBoard//beta
```

### With desktop write in not-Gnome Desktops 

Deb package builds for debian 9 and 10: http://packages.it-zukunft-schule.de/debian/pool/main/o/openboard/
```sh
$ sudo dpkg -i openboard_1.5.1+dfsg1-1~0deb9+itzks2_amd64.deb \ 
            openboard-common_1.5.1+dfsg1-1~0deb9+itzks2_all.deb \ 
            openboard-dbgsym_1.5.1+dfsg1-1~0deb9+itzks2_amd64.deb
$ sudo apt-get -f install
```
run with
```sh
$ OpenBoard
```

## OBS studio
https://obsproject.com/: Free and open source software for video recording and live streaming. 
The scenes can be designed. Good sound quality
```bash
sudo add-apt-repository ppa:obsproject/obs-studio
sudo apt update
sudo apt install obs-studio
```

## simplescreenrecorder
Good sound quality
```bash
sudo apt install simplescreenrecorder
```

## Kazam
While Kazam is running, you can use the following hotkeys:
1. Super+Ctrl+r: __Start__ recording.
1. Super+Ctrl+p: __Pause__ recording, press again for resuming the recording.
1. Super+Ctrl+f: __Finish__ recording.
1. Super+Ctrl+q: __Quit__ recording.


## Google Chrome

### Choose a not Default profile
```sh
google-chrome-stable --profile-directory=NewProfile
```
### Configure your browser to use an external socket
Suppose that you want to connect to internet through the network of a remote server.com.
Then you need to activate a socket through some port, like 1080, in your account in the remote computer
```sh
ssh -C2qTnN -D 1080 -4 user@server.com
```
Then you can configure your local browser to use the the network of the remote server.com. For example
```
 brave-browser  --proxy-server="socks5://localhost:1080"
 ```
 or by the proxy seeting of Firefox with the manual `socks5` option
 
 ## Inkscape
 * [Feynman Rules](https://graphicdesign.stackexchange.com/q/107442/153312)
 * [Bend from clipboard](https://graphicdesign.stackexchange.com/a/103086/153312)
 ![bend](https://i.stack.imgur.com/ZIt1D.gif)
 
 ## KDE
 Recover Windows (Super) key normal behaviour, instead of `<Alt>+<F1>`

Install: https://github.com/hanschen/ksuperkey
 
## Fast remote desktop
https://www.nomachine.com/download/download&id=2

## Creates bootable USB drive
Use [Etcher](https://www.balena.io/etcher/):
> Flash OS images to SD cards & USB drives, safely and easily.
Debian [install](https://github.com/balena-io/etcher#debian-and-ubuntu-based-package-repository-gnulinux-x86x64)
