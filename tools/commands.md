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
