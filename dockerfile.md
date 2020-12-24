# Dockerfile

Usado para buildar imagens e customizar, conforme necessidade

### FROM

Referencia uma imagem base

```
FROM <nome-imagem>:<tag>

FROM redis:lastest
```


### ENV

Cria uma variavel de ambiente para ser usada dentro do escopo da imagem

```
ENV <chave>=<valor>
ENV NOME_BUCKET="meu-bucket"
```

### RUN

Executa um comando para buildar

```
RUN echo "Bom dia"

RUN ls -lha

RUN apt-get install -y \
    apache2 && \
    mysql-server
```

### COPY

Permite copiar pasta ou arquivos da maquina 'HOST' para a imagem

```
COPY <origem> <destino>
COPY minha-pastar/ /home/meu-usuario/minha-pasta-destino
COPY meu-aquivo.txt /home/meu-usuario/
```

### ENTRYPOINT

Define o ponto de entrada, quando executar o docker run o primeiro lugar a ser procurado será o ENTRYPOINT

### CMD

### EXPOSE

### LABEL

Permite criar assinaturas de chave e valor

```
LABEL <chave> <valor>
LABEL maintainer 'Allan Gonçalves da Cruz <allangcruz@gmail.com>'
```

### ARG

Permte alterar um valor ao buildar a imagem ou definir um padrão


### USER


### WORKDIR


### VOLUME

### Buildar imagem

Versão com sintaxe antiga

```
docker build -t <nome-imagem>:<tag> -f Dockerfile .

ou

docker build --tag <nome-imagem>:<tag> --file Dockerfile .
```

Versão com sintaxe nova

```
docker image build -t <nome-imagem>:<tag> -f Dockerfile .

ou

docker image build --tag <nome-imagem>:<tag> --file Dockerfile .
```