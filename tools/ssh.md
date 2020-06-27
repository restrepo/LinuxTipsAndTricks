# ssh
## ssh tunnel
Open the tunnel from home computer with user guest  to a server running ssh server.com in standard port 22 and with external IP through the port 1080
```bash
guest@home~$ ssh -R *:1800:localhost:22 user@server.com
password:
user@server~$ #server console
```
Now,from any terminal in any other place, once you are connected to the server,  the connection to home computer is done with
```bash
user@server~$ ssh guest@localhost -p 1800 
password:
guest@home~$ #home console
```
See https://unix.stackexchange.com/a/101817/288558
