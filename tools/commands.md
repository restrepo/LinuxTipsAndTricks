# Shell Commands
## du
* Check for large files
```bash
du -h --max-depth=1 | grep -E '^[0-9\.]+G'
```
