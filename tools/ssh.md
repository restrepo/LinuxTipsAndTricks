# ssh
## ssh tunnel
Open the tunnel through the port 1080, from the home computer with user guest to the server.com running ssh in standard port 22, and with external IP. 
```bash
guest@home~$ ssh -R *:1800:localhost:22 user@server.com
password:
user@server~$ #server console need to be keeping open to listen port 1080
```
Now, from any terminal in any other place, once you are connected to the server,  the connection to the home computer is done with
```bash
user@server~$ ssh guest@localhost -p 1800 
password:
guest@home~$ #home console
```
See https://unix.stackexchange.com/a/101817/288558
