PopCoin
=========
Installation on Debian
-------
  - Add backports repository
  - Install docker
  - Test if docker works

First we need to enable the backports repository

On **jessie** we add the following line to **/etc/apt/sources.list**
```sh
deb http://ftp.debian.org/debian jessie-backports main
```
On **wheezy** we add the following line to **/etc/apt/sources.list**
```sh
deb http://ftp.debian.org/debian wheezy-backports main
```

Install curl
```sh
sudo apt-get update
sudo apt-get install curl
```
Add following GPG key
```sh
sudo curl -fsSL https://yum.dockerproject.org/gpg | sudo apt-key add -
```
Download the desired docker engine from [https://apt.dockerproject.org/repo/pool/main/d/docker-engine/](https://apt.dockerproject.org/repo/pool/main/d/docker-engine/)
```sh
sudo wget https://apt.dockerproject.org/repo/pool/main/d/docker-engine/<package>
sudo apt-get update
sudo dpkg -i <package>
```
Following lines are an example for debian jessie on ARM processor architecture
```sh
sudo wget https://apt.dockerproject.org/repo/pool/main/d/docker-engine/docker-engine_1.13.0-0~debian-jessie_amd64.deb  
sudo apt-get update
sudo dpkg -i docker-engine_1.13.0-0~debian-jessie_amd64.deb 
```
Install missing dependencies
```sh
sudo apt-get -f install
```
Now we can test if docker works by starting a container with the hello-world image
```sh
sudo docker run hello-world
```