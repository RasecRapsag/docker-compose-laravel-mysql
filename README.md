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


### Configurando ambiente

No arquivo .env definimos algumas configurações do nosso ambiente:

```bash
APP_DIR=./code
APP_USER=user

DOCKER_ETC=./etc/docker
DOCKER_PHP=Dockerfile.php-fpm
DOCKER_CONSOLE=Dockerfile.console

NGINX_VERSION=latest
NGINX_NAME=web
NGINX_PORT=80
NGINX_CONF=./etc/default.conf

MYSQL_VERSION=5.7
MYSQL_NAME=db
MYSQL_PORT=3306
MYSQL_PASSWORD=123456
MYSQL_DB=teste
MYSQL_DATA=./data

COMPOSE_HTTP_TIMEOUT=1000
```

Abaixo temos as configurações mais importantes:

- APP_DIR

Define a pasta que ficará o código do Laravel.

- APP_USER

Define o seu usuário utilizado no Linux, com isso todo o conteúdo gerado no console já terá permissão de escrita, não sendo necessário usar chown.

- NGINX_PORT

Define a porta de acesso da aplicação pelo browser.

- MYSQL_PASSWORD

Define a senha para acesso ao Mysql

- MYSQL_PORT

Define a porta de acesso ao Mysql.

- MYSQL_DB

Define o nome do banco de dados

- MYSQL_DATA

Define a pasta onde ficarão os arquivos do Mysql.


### Subindo os serviços

```bash
$ docker-compose up -d
```



## Comandos

Criei alguns atalhos para manipular os serviços definidos no docker-compose.

> **Nota**:
>
> Os comandos abaixo foram testados apenas no Linux e será necessário instalar o pacote make para funcionar. Em outro sistema operacional terá que utilizar os comandos do docker-compose que se encontram no arquivo Makefile.


- Para subir os serviços

```bash
$ make up
```

- Para derrubar os serviços

```bash
$ make down
```

- Para dar restart nos serviços

```bash
$ make restart
```

- Para listar os serviços

```bash
$ make ps
```

- Para verificar os logs

```bash
$ make logs
```

- Para acessar o console (executar comandos do Laravel)

```bash
$ make console
```



## Comandos no console

Dentro do console podemos utilizar alguns comandos, abaixo temos alguns exemplos:


- Cria um projeto Laravel no diretório /code que foi definido em APP_DIR

```bash
$ create-laravel
```

- Acessa o shell do MongoDB

```bash
$ mysql-cli
```

- Executando funções do Laravel

```bash
$ php artisan migrate
```

- Utilizando o Gerenciador de Dependências do PHP

```bash
$ composer require "laravelcollective/html":"^5.4.0"
```

- Utilizando o Gerenciador de Pacotes do Node

```bash
$ npm install vuex
```

- Utilizando o Controlador de Versão Git

```bash
$ git init
```
