# tor network
## Joint to the tor network
Creates onion addresses for a web server already running in port 80, and for a ssh server. The host computer can be well inside of an internal network!

See [here]() and [hera]() for details

1) Install tor to joint the tor network as a client (as the default behaviour)
```
sudo apt install tor
```
Check that tor is up and running. Open a google-chrome like browser with the tor default socket
```
 brave-browser --proxy-server="socs5://127.0.0.1:9051"
```
and go to https://httpbin.org/ip to check that your connection is from some tor exit node IP.

2) Uncomment and modify the following lines in your '/etc/tor/torrc' file
```
HiddenServiceDir /var/lib/tor/hidden_service/
HiddenServicePort 80 127.0.0.1:80

HiddenServiceDir /var/lib/tor/ssh_hidden_service/
HiddenServicePort 22 127.0.0.1:22
```
3) Created the `hidden` directories with the proper permissions
```
sudo mkdir -p /var/lib/tor/hidden_service/
sudo mkdir -p /var/lib/tor/ssh_hidden_service/
sudo chmod 0700 /var/lib/tor/hidden_service/
sudo chmod 0700 /var/lib/tor/ssh_hidden_service/
```
4) Restart the tor service
```
sudo service tor restart
```
and check that step 1) is still workign and that files `hostname` and `private` are generated in each hidden directory.

5) Get check the onion hostname from `/var/lib/tor/hidden_service/hostname` and check from any other computer in the tor network (with tor installed as in step 1), with the proper onion url:
```bash
torify curl -v http://1abvdefghijklm3l.onion/
```
5) Get check the onion hostname from `/var/lib/tor/ssh_hidden_service/hostname` and check from any other computer in the tor network (with tor installed as in step 1), with the proper onion url:
```bash
torify ssh http://2abvdefghijklm32.onion/
```
