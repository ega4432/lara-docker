# lara-docker

![Docker Image CI](https://github.com/yossiee/lara-docker/workflows/Docker%20Image%20CI/badge.svg)

## Overview
This is a repository for building Laravel environment with docker (docker-compose).
The base container image of the software used and its version are as follows.

| Software | base container image |
| :---: | :---: |
| php | [7.3-fpm-alpine](https://hub.docker.com/_/php) |
| mysql | [8.0](https://hub.docker.com/_/mysql) |
| nginx | [1.17-alpine](https://hub.docker.com/_/nginx) |
| redis | [5.0-alpine](https://hub.docker.com/_/redis) |
| node | [13.10-alpine](https://hub.docker.com/_/node) |

## Setup
### Requirements

```
❯ docker -v
Docker version 19.03.5, build 633a0ea

❯ docker-compose -v
docker-compose version 1.24.1, build 4667896b
```

### Build and Up

```
❯ docker-compose build
❯ docker-compose up -d
```

or

```
❯ docker-compose up -d --build
```

### Excute command

```
❯ docker-compose exec app [ service name ] ash [ command ( ex: php -v ) ]
```

### Stop and Remove containers

```
❯ docker-compose down
```

## Install Laravel

```
❯ docker-compose exec app ash
/work # composer create-project --prefer-dist "laravel/laravel=6.0.*" .

/work # php artisan -V
Laravel Framework 6.6.1
```

## Supplements
### Connect to MySQL

```
$ docker-compose exec db bash -c 'mysql -uroot -p${MYSQL_PASSWORD} ${MYSQL_DATABASE}'
```
