# Cluster_Kubernte
Modelo em KINDE de um cluster Kubernete integrando uma imagem de uma api de um CDRUD e uma base Postgres mantendo Resiliencia e escalabilidade

## Prerequisites

Please refer to RabbitMQ documentation to learn
more about various [installation options](https://www.rabbitmq.com/download.html):

 *  [KIND](https://kind.sigs.k8s.io/)
 * [Docker](https://www.docker.com/)
 * [Imagem API](https://hub.docker.com/repository/docker/developer10/api-futiuber) 
 
 
### Development

Abra seu terminal e execute estes comandos.

Em nome_do_seu_cluster substitua pelo nome que desejar:
```sh
kind create cluster --name=nome_do_seu_cluster
```

Second Tab:
```sh
$ gulp watch
```

(optional) Third:
```sh
$ karma test
```


