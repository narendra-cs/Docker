# Docker Basic

## Prerequisite
* System : 64 bit
* Kernel : >=3.10

## Installation :
  * [Centos 7 /RHEL 7 ] [centos_install]
  * [Ubuntu 16.04 ] [ubuntu_install]

The Docker installation package available in the official CentOS 7 repository may not be the latest version. To get the latest and greatest version, install Docker from the official Docker repository.


update the package database:

```bash
# yum update
```

Now run this command. It will add the official Docker repository, download the latest version of Docker, and install it:

```bash
# curl -fsSL https://get.docker.com/ | sh
```

start the Docker daemon:

```bash
# systemctl start docker
```

Verify that it's running:

```bash
# systemctl status docker
```

make sure it starts at every server reboot:
 
```bash
# systemctl enable docker
```

check docker version:

```bash
# docker --version
```

## Manage Docker as a non-root user

**NOTE:** if you want to run docker from non root or without sudo account add user to docker group 

```bash
# usermod -aG docker <user_name>
```
now <user_name> will able to use docker

we have to do the above activity beacuse ownership of docker.sock file in /var/run is root:docker withour root or a user that is in docker group will not allowed to use the docker.sock file to connect to docker socket.
for more info about security read : 
  
  
  
  
  
  
[centos_install]:https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-centos-7 "How To Install and Use Docker on CentOS 7"
[ubuntu_install]:https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-16-04 "How To Install and Use Docker on Ubuntu 16.04"
