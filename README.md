# HRM 

This is a instruction to set up enviroment to work in HRM-NAL project

## Installation Docker and virtualize Centos server 

We use Docker so firstly, we need to install [Docker](https://docs.docker.com/docker-for-windows/install/) (this is for Windows)

When we had the Dockerfile at the direct folder [here](https://github.com/thimcusu/docker-hrm)
1. Pull centos:7 image : `docker pull centos:7`
2. Run this to pull OS Centos: 
```
	docker build --rm -t centos7-systemd .
```
  You might run: ` docker images ` to check images pulled.
 
3. Run *centos7-systemd* container:
 
```
	docker run --privileged  -ti -e container=docker  -v /sys/fs/cgroup:/sys/fs/cgroup  centos7-systemd /usr/sbin/init
```
  - Show containers is running `docker ps`
4. Access to OS Centos:
```
	sudo docker exec -it '[container_name/container_id]' /bin/bash
```
## Installation Docker in virtual Centos
Now, we need docker and docker-compose in Centos, check [here](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-centos-7). And also, [docker-compose](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-centos-7)

### Docker for Laravel project
 **Note**: You might need install some packages. Run `yum install '<package_name>'` 
#### Step 1 - Direction laravel project 
 * `cd home` 
 * `yum install git` 
 *Clone Laravel project:
`git clone https://github.com/laravel/laravel.git laravel-app` 
 * Move into the **laravel-app** directory:
      `$ cd laravel-app`
#### Step 2 — Creating the Docker-compose.yml file
 * Create [*docker-compose.yml*](https://github.com/thimcusu/docker-hrm/blob/main/docker-compose.yml) file
```nano docker-compose.yml
```
#### Step 3 — Creating the Dockerfile
  * Create [Dockerfile](https://github.com/thimcusu/docker-hrm/blob/main/php/Dockerfile): 
     `$ nano ~/laravel-app/Dockerfile`
#### Step 4 — Configuring PHP
  * Create a **php** direction: `mkdir php`
  * Open [local.ini](https://github.com/thimcusu/docker-hrm/blob/main/php/local.ini) file: `nano /php/local.ini`
#### Step 5 — Configuring Nginx
  * Create [nginx/conf.d/app.conf](https://github.com/thimcusu/docker-hrm/blob/main/nginx/app.conf) file: 
        $ `mkdir -p /nginx/conf.d/`
        $ `nano /nginx/conf.d/app.conf`
#### Step 6 — Configuring MySQL
  * Create [mysql/my.cnf](https://github.com/thimcusu/docker-hrm/blob/main/mysql/my.cnf)
        $ `mkdir mysql` 
        $ `cd mysql`
        $ `nano my.conf`
### Step 7 - Modifying Environment Settings and Running the Containers
        $ `cp .env.example .env`
        $ `nano .env`
## Run Containers
```
    docker-compose up -d 
```
Once the process is complete, use the following command to list all of the running containers:
``` 
    docker ps
```


