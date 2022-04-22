## Utilizando RABBITMQ com DOCKER

### Baixar última versão do RabbitMQ

```
$ docker run -it --rm  --network db-newtork --name rabbitmq -p 5672:5672 -p 15672:15672 -v /var/rabbitmq-storage rabbitmq:3.8-management

```

##### pesquisar mais sobre a persistencia de dados, volumes, etc
