# Shell Commands
## du
* Check for large files
```bash
du -h --max-depth=1 | grep -E '^[0-9\.]+G'
```
## `while` instead of `for`
[Here](https://stackoverflow.com/a/414316)'s a script that uses GNU sort's random option:
```bash
ls |sort -R |tail -$N |while read file; do
    # Something involving $file, or you can leave
    # off the while to just get the filenames
done
```
## Shell script to display output and store at same time
See https://stackoverflow.com/a/8303599/2268280
```bash
./script.sh 2>&1 | tee -a out.txt
```
## Check if TCP port is open
For example the port 100
```bash
telnet portquiz.net 100
```
with timeout of 5s
```bash
echo quit | timeout --signal=9 5 telnet portquiz.net 100
```
## List partitions of all devices
```bash
lsblk
```
## Change root
1. Mount a linux partition to use `chroot`, e.g `/dev/sda5`
```bash
sudo mount /dev/sda5 /mnt
```
2. Mount critical virtual filesystems:
```bash
 for i in /dev /dev/pts /proc /sys /run; do sudo mount -B $i /mnt$i; done
```
3. `chroot` into the Linux partition you mounted:
```bash
sudo chroot /mnt
```
See https://askubuntu.com/a/946155 which includes one explanation to use this method to install grud in an external hard disk

## Add swap file
From https://askubuntu.com/a/178726
1. Create empty file:
This file will contain virtual memory contents so make file big enough for your needs. This one will create 1Gb file which means +1Gb swap space for your system:
```bash
dd if=/dev/zero of=/media/fasthdd/swapfile.img bs=1024 count=1M
```
If you want to make 3Gb file then change count value to count=3M. See man dd for more information.

2. Bake swap file:
Following command is going to make "swap filesystem" inside your fresh swap file.
```bash
mkswap /media/fasthdd/swapfile.img
```

3. Activate:
You can either reboot your computer or activate new swap file by hand with following command:
```bash
swapon /media/fasthdd/swapfile.img
```

4. Bring up on boot:
To make sure that your new swap space is activated while booting up computer you should add it to filesystem configuration file /etc/fstab. Add it to end of file, this is recommended because other filesystems (at least one that contains swap file) must be mounted in read-write mode before we can access any files.

```bash
# Add this line to /etc/fstab
/media/fasthdd/swapfile.img swap swap sw 0 0
```

## How to kill a process running on particular port in Linux?
See: https://stackoverflow.com/a/32592965/2268280
```bash
kill $(lsof -t -i:8080)
```
##  How to know whether Wayland or X11 is being used
https://unix.stackexchange.com/a/325972/288558
```bash
loginctl show-session <SESSION_ID> -p Type
```

## Reduce the file size of PDF file
See: https://askubuntu.com/a/256449
```
gs -sDEVICE=pdfwrite -dCompatibilityLevel=1.4 -dPDFSETTINGS=/ebook \
-dNOPAUSE -dQUIET -dBATCH -sOutputFile=output.pdf input.pdf
```
Summary of `-dPDFSETTINGS`:

* `-dPDFSETTINGS=/screen` lower quality, smaller size. (72 dpi)
* `-dPDFSETTINGS=/ebook` for better quality, but slightly larger pdfs. (150 dpi)
* `-dPDFSETTINGS=/prepress` output similar to Acrobat Distiller "Prepress Optimized" setting (300 dpi)
* `-dPDFSETTINGS=/printer` selects output similar to the Acrobat Distiller "Print Optimized" setting (300 dpi)
* `-dPDFSETTINGS=/default` selects output intended to be useful across a wide variety of uses, possibly at the expense of a larger output file




