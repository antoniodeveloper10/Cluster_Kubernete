# Cluster_Kubernete
Projeto em KIND contendo resiliência e escalabilidade de um cluster Kubernete integrando uma api e uma base PostgreSQL 

## Requisitos

 *  [KIND](https://kind.sigs.k8s.io/)
 * [Docker](https://www.docker.com/)
 * [Imagem API](https://hub.docker.com/repository/docker/developer10/api-futiuber) 
 
 
### Criação
Faça a copia e abra o projeto
no terminal da sua IDE execute estes comandos.

Em **nome_do_seu_cluster** substitua pelo nome que desejar:
```sh
kind create cluster --name=nome_do_seu_cluster
```

Suba o deployment da base 
```sh
kubectl apply -f base/deplyment.yaml
```

Suba o serviço da base 
```sh
kubectl apply -f base/service.yaml
```

**(opcional)** caso queira acessar a base pelo seu computador execute o **port-forward**
```sh
kubectl port-forward service/db  5432:5432
```

Suba o deployment da API 
```sh
kubectl apply -f api/deplyment.yaml
```

Suba o serviço da API 
```sh
kubectl apply -f api/service.yaml
```

Para acessar a API pelo seu computador execute o **port-forward**
```sh
kubectl port-forward service/api-service  8000:8000
```

Para acessar a API  barra do navegador 
```sh
digite http://127.0.0.1:8000/
```
Para acessar o painel de Admin da API
```sh
digite http://127.0.0.1:8000/admin
```
E entre com os dados de usuário setados no deplyment.yaml da api

