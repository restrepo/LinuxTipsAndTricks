# Docker
See installations instructions here: https://github.com/restrepo/docker-udea, including `docker-compose` install

[My Help](https://github.com/restrepo/docker-udea/blob/master/help.md)

To clean all the containers:
see https://linuxize.com/post/how-to-remove-docker-images-containers-volumes-and-networks/
```sh
$ docker system prune
```

## Example VNC:
See: https://github.com/ConSol/docker-headless-vnc-container
### Official image for ubuntu 16.04
To install and run as root:
```sh
$ sudo docker run -d -p 5901:5901 -p 6901:6901 --user 0 consol/ubuntu-xfce-vnc
```
or change `ubuntu` by `centos`.

Conect to 
```sh
$ vncviewer localhost:5901  #default password: vncpassword
```
or via web to http://localhost:6901/?password=vncpassword

See [My Help] for the image/container management.

### Customized image
* Creates Dockerfile in `./Dockerfile`
Use `exit 0` to allow the `RUN` of commands with errors (See https://stackoverflow.com/a/30717108)
```sh
## Custom Dockerfile
FROM consol/ubuntu-xfce-vnc
ENV REFRESHED_AT 2018-03-18

# Switch to root user to install additional software
USER 0

RUN apt-get update
RUN wget https://github.com/OpenBoard-org/OpenBoard/releases/download/v1.5.4/openboard_ubuntu_16.04_1.5.4_amd64.deb 2> /dev/null
RUN ls openboad_ubuntu_16.04_1.5.4_amd64.deb
RUN dpkg -i openboard_ubuntu_16.04_1.5.4_amd64.deb; exit 0
RUN apt-get -yf install 
```

* Build the image (see https://stackoverflow.com/a/36076856)
```sh
docker build -t openboard .
```
* Check the image
```sh
$ docker image ls
REPOSITORY               TAG                 IMAGE ID            CREATED             SIZE
openboard                latest              54********        37 seconds ago      1.45GB
```
* run the image:
```sh
$ docker run -d -p 5901:5901 -p 6901:6901 --user 0 openboard
```
Conect to 
```sh
$ vncviewer localhost:5901  #default password: vncpassword
```
or via web to http://localhost:6901/?password=vncpassword

See [My Help] for the image/container management.

### Forked image for ubuntu 18.04
To install and run as root: (See: https://hub.docker.com/r/wittyfinch/ubuntu-vnc)
```sh
docker run -d -p 5901:5901 --user 0 wittyfinch/ubuntu-vn
```

## Example Overleaf:
Tu run [Overleaf docker](https://github.com/overleaf/overleaf)
* Install docker: `$ sudo docker pull sharelatex/sharelatex` 
* Clone overleaf repo:
```sh
$ git clone https://github.com/overleaf/overleaf.git
$ cd overleaf
```
* Stop `apache2` to free port 80 or change in `docker-compose.yml` the line with the `ports:` to `8080:80`
* Use the repo `docker-compose.yml` file to get up and running: (See [here](https://medium.com/@shuangzizuobh2/host-your-own-latex-server-a-docker-example-2787531bf93b) for details)
```bash
$ sudo docker-compose up
```
If everything works out fine, you should be able to connect to your local overleaf server at http://localhost:8080
* Creating and Managing users:
```bash
sudo docker exec sharelatex /bin/bash -c "cd /var/www/sharelatex; grunt user:create-admin --email=joe@example.com"
```
See https://github.com/overleaf/overleaf/wiki/Quick-Start-Guide for details like: 
This will create a user with the given email address if they don't already exist, and make them an admin user. 
You will be given a URL to visit where you can set the password for this user and log in for the first time. 
Login with the email. 

