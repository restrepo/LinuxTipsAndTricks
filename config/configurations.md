# Terminal
## How to turn off the beep only in bash tab-complete
Editing `/etc/inputrc`
```bash
set bell-style none
```
# Desktop
## Locales configuration
Search Latinamerican keyboar in English locale. 
To configure for several flavors of Spanish and English use:
```bash
# dpkg-reconfigure locales
```
and choose `es_ES.utf8`, `es_ES.utf8`, and `us_US.utf8`

