# Estudos sobre o mundo frenético de Docker

## O que é?
É uma ferramenta para criar e manter *containers*, ou seja, ele é responsável por armazenar vários serviços de forma isolada do SO host, como: web server, banco de dados, aplicação, memcached etc.

Para saber mais sobre o docker verifique a [introdução](https://github.com/Allangcruz/docker-estudos/blob/master/indroducao.md)

## Como instalar?

- ### Linux

# Comandos basicos docker client

### Exibe a versão do arquivo
```
docker --version
```

### Lista as images baixadas de algum register
```
docker images
```

### Autentica o acesso do docker em um register privado, para permitir subir images
```
docker login <url-register>
```

Autentica especificando o usuario e senha (token criado não senha)

```
docker login <url-register> \
    --username <seu-login-no-github> \
    --password <seu-personal-access-token>
```

### Baixa a imagem do repositorio remoto (docker-hub, git-package, harbor)
```
docker pull <nome-imagem>:<tag>
```

### Envia a imagem para repositorio remoto (docker-hub, git-package, harbor)
```
docker push <nome-imagem>:<tag>
```

### Constroi uma nova image, nomeando com uma tag, e especificando arquivo
```
docker build -t <nome-imagem>:<tag> -f Dockerfile .

ou

docker build --tag <nome-imagem>:<tag> --file Dockerfile .
```

### Constroi uma nova image, passando argumentos
```
docker build \
    --build-arg <chave>=<valor> \
    --build-arg <chave>=<valor> \
    -t <nome-imagem>:<tag> -f Dockerfile .
```

### Executa um container
```
docker container run <nome-imagem>:<tag>
```

### Executa um container, especificando o nome do container
```
docker container run --name <nome-imagem> <nome-imagem>:<tag>
```

### Executa um container, especificando o nome do container, e apos a execução exclui o container (--rm)
```
docker run --rm --name <nome-imagem> <nome-imagem>:<tag>
```

### Executa um container, especificando o nome do container, e apos a execução exclui o container (--rm), executa em modo interativo
```
docker run \
    --rm \
    -it \
    --name <nome-imagem> \
    <nome-imagem>:<tag>
```

### Executa um container, especificando o nome do container, e apos a execução exclui o container (--rm), executa em modo interativo, especifica arquivo de variavel de ambiente, ou uma variavel de ambiente pontual
```
docker run \
    --rm \
    -it \
    --name <nome-imagem> \
    --env-file <path-arquivo-env> \
    --env <chave-env>=<valor-env> \
    -e <chave-env>=<valor-env> \
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
docker run \
    --rm \
    -it \
    --publish 8000:8080 \
    --name <nome-imagem> \
    --env-file <path-arquivo-env> \
    -p <porta-host>:<porta-container> \
    -v <path-host>:<path-container> \
    <nome-imagem>:<tag>
```

```
docker run \
    --rm \
    -it \
    --publish 8000:8080 \
    --detach \
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