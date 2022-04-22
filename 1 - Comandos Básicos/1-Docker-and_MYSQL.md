## Utilizando MYSQL com DOCKER

### Baixar última versão do mysql

```
$ docker pull mysql:lastest
```

### Listar todas imagens

```
$ docker images
```

### Deploy do container especificando váriaveis de ambiente (-e) e rodando em background (-d)

```
$ docker run --name mysql-container -e MYSQL_ROOT_PASSWORD=root -d mysql:latest
```

### Listar todos containers deployados

```
$ docker ps -a
```

### Copiar arquivo com dump para o container

```
$ docker cp .\myCommerce.sql mysql-container:/tmp/
```

### Acessar diretamente o container via terminal

```
$ docker exec -it mysql--container bash
```

### Criar banco de dados e restaurar arquivo de dump.

```
$ cd /tmp
$ mysql --user=root --password=root
$ use mysql;
$ show databases;
$ CREATE DATABASE  ‘testedb’
$ use testedb;
$ source \myCommerce.sql;
$ show tables;
$ \q
$ exit;
```

## PhpMyAdmin

$ docker pull phpmyadmin

$ docker run --name phpmyadmin-container -d --link mysql-container:db -p 8081:80 phpmyadmin
