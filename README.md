
## Instalação

Passo 1 - Clone o projeto

Passo 2 - Dentro da pasta /src onde está o arquivo Dockerfile rode os comandos

```bash
#lista as imagens criadas
docker image ls

#gera a imagem da aplicação
docker image build -t seu_id/conversor-temperatura-desafio-02:v1 .

#lista as imagens criadas
docker image ls

#gera a versão latest da versão 1 (Boa prática)
docker tag seu_id/conversor-temperatura-desafio-02:v1 seu_id/conversor-temperatura-desafio-02:latest

#faz login no dockerhub
docker login

#envia a imagem para o dockerhub
docker push seu_id/conversor-temperatura-desafio-02:v1

#envia a imagem para o dockerhub
docker push seu_id/conversor-temperatura-desafio-02:latest

#lista os container em exeção
docker container ls
```

Passo 3 - Agora navege até a pasta k8s e dentro dela rode os seguintes comandos:

```bash
#cria os agentes de servidores do cluster com seus agentes e servidores para a redundância
k3d cluster create cluster-conversor-temperatura --agents 2 --servers 2 -p "8080:30000@loadbalancer"

#le o arquivo para executar as instruçoes
kubectl apply -f deployment.yaml

#lista os nós
kubectl get pods

#lista os serviços
kubectl get services
```

Passo 4 - Abrir o navegador e acessar o endereço localhost:8080
    