# Docker Compose Laravel MySQL

## Introdução

Criação de um ambiente para de desenvolvimento utilizando:

* [Docker](https://www.docker.com)
* [Nginx](http://nginx.org)
* [PHP 7](https://php-fpm.org)
* [Laravel](https://laravel.com)
* [MySQL](https://www.mysql.com)


Para criação do nosso ambiente, será necessário que o Docker e o Docker Compose estejam instalados no nosso sistema Linux.


### Instalação Docker

```bash
$ sudo curl -fsSl https://get.docker.com | bash
```


### Instalação Docker Compose

```bash
$ sudo curl -L https://github.com/docker/compose/releases/download/1.17.0/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
$ sudo chmod 755 /usr/local/bin/docker-compose
```


### Clonando repositório

```bash
$ mkdir ~/App && cd ~/App
$ git clone https://github.com/RasecRapsag/docker-compose-laravel-mysql
$ cd docker-compose-laravel-mongodb/
```
