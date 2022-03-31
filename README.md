# Desafio 02 (Iniciativa Kubernetes)

Este desafio consiste em criar o processo de execução no Docker de uma aplicação simples construida em Node.Js que tem como foco converter uma temperatura de Celsius para Fahrenheit e vice e versa.

## Requisitos

Ter o Node.Js e Docker instalado na sua máquina. Após isso, siga o passo a passo abaixo

1 - Clone ou baixe o repositório, abra a pasta src instale as dependencias e rode o projeto local para ter certeza que tudo está OK
```bash
cd desafio_01_iniciativa_kubernetes
cd src
npm install
node server.js
```
Feito o passo 1, é hora de começar a usar o Docker...

## Comandos Docker
2 - Dentro da pasta /src rode os comando abaixo:

```python
# comando irá gerar uma imagem do projeto seguindo o arquivo Dockerfile
docker image build -t diego64/conversor-temperatura-desafio-01:v1 .

# comando irá pegar a imagem criada acima e rodar em um container
docker container run -d -p 8080:8080 seu_id/conversor-temperatura-desafio-01:v1
```
3 - Alguns comandos para consulta

```python
# comando irá listar as imagens criadas (Pode acrescentar -a no final)
docker image ls

# comando irá listar os container criados (Pode acrescentar -a no final)
 docker container ls
```

4 - Caso queira deletar uma imagem ou container

```python
# comando irá deletar uma imagem criadas (Substituía os 000000 pelo ID da sua imagem)
docker image rm 000000

# comando irá deletar um container criado (Substituía os nome_do_seu_container pelo nome do seu container)
docker container rm nome_do_seu_container
```

## Para subir a imagem criada para o Dokerhub
```python
# comando irá logar sua conta do dokerhub
docker login

# comando irá enviar a imagem para o repositório do docker
docker push seu_id/nome_da_aplicacao:v1
```

## Para baixar a imagem do projeto e rodar na sua maquina
```python
# comando irá logar sua conta do dokerhub
docker login

# comando irá buscar no meu dockerhub
docker container run -d -p 8080:8080 diego64/conversor-temperatura:v1
```

Please make sure to update tests as appropriate.

## Créditos
Fabrício Veronez - Instrutor da Iniciativa Kubernetes (https://iniciativakubernetes.com.br/)