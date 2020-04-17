# Docker
See installations instructions here: https://github.com/restrepo/docker-udea, including `docker-compose` install

## Example:
Tu run [Overleaf docker](https://github.com/overleaf/overleaf)
* Stop `apache2` to free port 80 or change in `docker-compose.yml` the line with the `ports:` to `8080:80`
* Install docker: `$ sudo docker pull sharelatex/sharelatex` 
* Clone overleaf repo:
```sh
$ git clone https://github.com/overleaf/overleaf.git
$ cd overleaf
```
* Use the repo `docker-compose.yml` file to get up and running: (See [here](https://medium.com/@shuangzizuobh2/host-your-own-latex-server-a-docker-example-2787531bf93b) for details)
```bash
$ sudo docker-compose up
```
If everything works out fine, you should be able to connect to your local sharelatex server at http://localhost:8080
* Creating and Managing users:
```bash
sudo docker exec sharelatex /bin/bash -c "cd /var/www/sharelatex; grunt user:create-admin --email=joe@example.com"
```
See https://github.com/overleaf/overleaf/wiki/Quick-Start-Guide for details like: 
This will create a user with the given email address if they don't already exist, and make them an admin user. 
You will be given a URL to visit where you can set the password for this user and log in for the first time. 
Login with the email. 

