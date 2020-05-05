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

## Kazam
While Kazam is running, you can use the following hotkeys:
1. Super+Ctrl+R: __Start__ recording.
1. Super+Ctrl+P: __Pause__ recording, press again for resuming the recording.
1. Super+Ctrl+F: __Finish__ recording.
1. Super+Ctrl+Q: __Quit__ recording.
