**I forked the project to adapt it for the Raspbian, the Debian flavor for Raspberry Pi**

## Nginx Dockerfile


There is no automated build for the Raspberry Pi, as far as I know.


### Base Docker Image

* [dockerfile/ubuntu](http://dockerfile.github.io/#/ubuntu)


### Installation

1. Install [Docker](https://www.docker.com/).

2. Build an image from Dockerfile: `docker build -t="dockerfile/nginx" github.com/taophp/nginx`)


### Usage

    docker run -d -p 80:80 dockerfile/nginx

#### Attach persistent/shared directories

    docker run -d -p 80:80 -v <sites-enabled-dir>:/etc/nginx/conf.d -v <certs-dir>:/etc/nginx/certs -v <log-dir>:/var/log/nginx -v <html-dir>:/var/www/html dockerfile/nginx

After few seconds, open `http://<host>` to see the welcome page.
