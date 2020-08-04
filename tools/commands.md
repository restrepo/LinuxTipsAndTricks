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
