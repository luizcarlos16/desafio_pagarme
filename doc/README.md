# DESAGIO_PAGAR.ME
Desafio Observabilidade Pagar.me

## Requirements

- [Python](https://www.python.org)
- [Prometheus](https://prometheus.io/)
- [Grafana](https://grafana.com/)
- [Docker](https://www.docker.com)
- [Docker Compose](https://docs.docker.com/compose/)
- [Git](https://git-scm.com/)
- [GitHub](https://github.com/)

## Desenvolvimento

### Execute o projeto com o Docker:

Vá para o terminal onde está a raiz do projeto e digite este comando.

```
docker-compose up
```

Mas, se você deseja executar o projeto e liberar o terminal, pode usar este comando.

```
docker-compose up -d
```

### Aplicação

- Criei uma imagem no DockerHub com da API:  docker pull thecalifornia16/desafio_pagarme

    - O Dockerfile da Api está na raiz e a api é o arquivo "api.py", foi desenvolvido um script "comentarios.sh" que incluir os comentarios automaticamente para ser validado na URL http://ip_server/api/comment/list/2 e http://ip_server/api/comment/list/1 

Obs: Tem um ambiente que deixei pronto para ser acessado e validado: http://177.38.215.196/api/comment/list/1 e http://177.38.215.196/api/comment/list/2

### Scripts criados para inserir os comentarios: 

- Após execução do container;
- Rodar o script "comentarios.sh" para inclusão dos comentarios 
    ```
                "sudo docker container exec desafio_pagarme sh comentarios.sh"
    ```

    * Criando e listando comentários por matéria
    # matéria 1
    ```
    curl -sv localhost:8000/api/comment/new -X POST -H 'Content-Type: application/json' -d '{"email":"alice@example.com","comment":"first post!","content_id":1}'
    curl -sv localhost:8000/api/comment/new -X POST -H 'Content-Type: application/json' -d '{"email":"alice@example.com","comment":"ok, now I am gonna say something more useful","content_id":1}'
    curl -sv localhost:8000/api/comment/new -X POST -H 'Content-Type: application/json' -d '{"email":"bob@example.com","comment":"I agree","content_id":1}'
    ```
    # matéria 2
    ```
    curl -sv localhost:8000/api/comment/new -X POST -H 'Content-Type: application/json' -d '{"email":"bob@example.com","comment":"I guess this is a good thing","content_id":2}'
    curl -sv localhost:8000/api/comment/new -X POST -H 'Content-Type: application/json' -d '{"email":"charlie@example.com","comment":"Indeed, dear Bob, I believe so as well","content_id":2}'
    curl -sv localhost:8000/api/comment/new -X POST -H 'Content-Type: application/json' -d '{"email":"eve@example.com","comment":"Nah, you both are wrong","content_id":2}'
    
    ```
    # listagem matéria 1
    ```
    curl -sv ip_server/api/comment/list/1
    ```
    # listagem matéria 2
    ```
    curl -sv ip_server/api/comment/list/2
    ```

## Prometheus

### Veja as métricas

As métricas da API podem ser vistas de maneiras mais organizadas e engenhosas, e podem ser vistas no Prometheus por meio deste endpoint:

```
http://localhost:9090/targets
```

Link Ativo:
```
http://177.38.215.196:9090/targets
```


## Grafana

### Veja as métricas

As métricas de uma API podem ser medidas pelo Promotheus. No entanto, seu painel não é tão intuitivo e não possui tantos recursos quanto o Grafana. Portanto, é interessante utilizá-lo para apresentar as métricas obtidas no Prometheus.

O Grafana está disponível neste endpoint:

```
http://localhost:3000
```

Link Ativo:
```
http://177.38.215.196:3000
```

### Acesso a Grafana

O Grafana tem maior segurança sobre os dados do que o Prometheus. Você precisa seguir estas etapas para acessar as métricas:

    - Usuário: admin
    - Senha: admin
    - Você pode pular a etapa de alterar a senha
    - O terceiro ícone do menu esquerdo é Dashboards
    - Escolha "Browse"
    - Em seguida, clique no dashboard "App Comentarios"
