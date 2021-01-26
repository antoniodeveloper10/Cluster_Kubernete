# Cluster_Kubernete
Projeto em KIND contendo resiliência e escalabilidade de um cluster Kubernete e orquestrando uma imagem de uma api criada em Django REST Framework e uma base contendo a imagem do PostgreSQL 

## Requisitos

 *  [KIND](https://kind.sigs.k8s.io/)
 * [Docker](https://www.docker.com/)
 * [Imagem API](https://hub.docker.com/repository/docker/developer10/api-futiuber) 
 
 
### Criação
No projeto abra o deployment.yam que esta na pasta api/
edite  suas variáveis de ambiente conforme suas credenciais e salve o arquivo. Estas informações permitiram acesso ao painel administrativo da API
```
        env:
          - name:  NOMEUSER
            value: seunome
          - name: EMAILUSER
            value: seu@email.com
          - name: PWDUSER
            value: suasenha 
```




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

Permitir acesso a API pelo seu computador execute o **port-forward**
```sh
kubectl port-forward service/api-service  8000:8000
```

Para acessar a API na barra do navegador 
```sh
digite http://127.0.0.1:8000/
```
Para acessar o painel de Admin da API
```sh
digite http://127.0.0.1:8000/admin
```
**E entre com os dados de usuário setados no deployment.yaml da api**

