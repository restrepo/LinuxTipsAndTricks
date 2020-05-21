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
### Connect trhough a socket
Let say to activate socket through a  port 1080
```sh
ssh -C2qTnN -D 1081 -4 host
```
Then use:
```
 brave-browser  --proxy-server="socks5://localhost:1080"
 ```
 
 ## Inkscape
 * [Feynman Rules](https://graphicdesign.stackexchange.com/q/107442/153312)
