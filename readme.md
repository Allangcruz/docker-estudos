# Estudos sobre o mundo frenético de Docker

## O que é?
É uma ferramenta para criar e manter *containers*, ou seja, ele é responsável por armazenar vários serviços de forma isolada do SO host, como: web server, banco de dados, aplicação, memcached etc.

Para saber mais sobre o docker verifique a [introdução](https://github.com/Allangcruz/docker-estudos/blob/master/indroducao.md)

## Como instalar?

- ### Linux

# Comandos basicos docker client

### Lista as images baixadas de algum register
```
docker images
```

### Autentica o acesso do docker em um register privado, para permitir subir images
```
docker login <url-register>
```

```
docker login <url-register>
```

```
docker pull <nome-imagem>:<tag>
```

```
docker push <nome-imagem>:<tag>
```

```
docker build -t <nome-imagem>:<tag> -f Dockerfile .
```

```
docker build \
    --build-arg <chave>=<valor> \
    --build-arg <chave>=<valor> \
    -t <nome-imagem>:<tag> -f Dockerfile .
```

```
docker run <nome-imagem>:<tag>
```

```
docker run --name <nome-imagem> <nome-imagem>:<tag>
```

```
docker run --rm --name <nome-imagem> <nome-imagem>:<tag>
```

```
docker run \
    --rm \
    -it \
    --name <nome-imagem> \
    <nome-imagem>:<tag>
```

```
docker run \
    --rm \
    -it \
    --name <nome-imagem> \
    --env-file <path-arquivo-env> \
    <nome-imagem>:<tag>
```

```
docker run \
    --rm \
    -it \
    --name <nome-imagem> \
    --env-file <path-arquivo-env> \
    -p <porta-host>:<porta-container> 
    <nome-imagem>:<tag>
```

```
docker run \
    --rm \
    -it \
    --name <nome-imagem> \
    --env-file <path-arquivo-env> \
    -p <porta-host>:<porta-container> \
    -v <path-host>:<path-container> \
    <nome-imagem>:<tag>
```

```
docker ps
```

```
docker ps -a
```

# Contribuidor
[Allangcruz](https://github.com/Allangcruz)