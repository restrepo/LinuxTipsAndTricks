# `tor` network
## Assign an onion `tor` addresses to a computer in a hidden internal network
Creates onion addresses for a web server already running in port 80, and for a ssh server in port 22. The host computer can be well inside of an internal network!

See [here](https://medium.com/@ajphillips/how-to-create-your-own-tor-hidden-service-436bece8602f) and [here](https://medium.com/@tzhenghao/how-to-ssh-over-tor-onion-service-c6d06194147) for details

1) Install tor to joint the tor network as a client (as the default behaviour)
```
sudo apt install tor
```
2) Check that `tor` is up and running. Open a google-chrome like browser with the `tor` (default) socket
```
 brave-browser --proxy-server="socs5://127.0.0.1:9051"
```
and go to https://httpbin.org/ip to check that your connection is from some `tor` _exit node_ IP.

3) Uncomment and modify the following lines in your `/etc/tor/torrc` file
```
HiddenServiceDir /var/lib/tor/hidden_service/
HiddenServicePort 80 127.0.0.1:80
HiddenServicePort 22 127.0.0.1:22
```
4) Created the `hidden` directories with the proper permissions
```
sudo mkdir -p /var/lib/tor/hidden_service/
chown debian-tor:debian-tor /var/lib/tor/hidden_service/ 
sudo chmod 0700 /var/lib/tor/hidden_service/
```
5) Restart the tor service
```
sudo service tor restart
```
and check that step 1) is still workign and that files `hostname` and `private` are generated in each hidden directory.

6) Get the onion hostname from `/var/lib/tor/hidden_service/hostname` and check it from any other computer in the tor network (with tor installed as in step 2), with the obtained onion hostname:
```bash
torify curl -v http://1abvdefghijklm3l.onion/
```
or try to load it with the [`tor` browser](https://www.torproject.org/download/), provided the Tor network isn't overloaded. 
7)  Check the ssh connection from any other computer in the tor network (with tor installed as in step 1), with the same onion hostname:
```bash
torify ssh http://1abvdefghijklm31.onion/
```
