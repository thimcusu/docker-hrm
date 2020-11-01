docker run -ti -v /sys/fs/cgroup:/sys/fs/cgroup:ro -p 80:80 local/c7-systemd-httpd
docker build --rm -t centos7-systemd - < mydockerfile

# HRM 

This is a instruction to set up enviroment to work in HRM-NAL project

## Installation

We use Docker so firstly, we need to install [Docker](https://docs.docker.com/docker-for-windows/install/) (this is for Windows)

