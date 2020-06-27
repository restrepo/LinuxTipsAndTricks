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

## Configure your browser to use an external socket
Suppose that you want to connect to internet through the network of a remote server.com.
Then you need to activate a socket through some port, like 1080, in your account in the remote computer
```sh
ssh -C2qTnN -D 1081 -4 user@server.com
```
Then you can configure your local browser to use the the network of the remote server.com. For example
```
 brave-browser  --proxy-server="socks5://localhost:1080"
 ```
 or by the proxy seeting of Firefox with the manual `socks5` option
